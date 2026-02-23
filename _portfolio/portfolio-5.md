---
title: "GAPO: Geometric Anchor Preference Optimization"
excerpt: "First-author research on geometry-aware robust preference alignment for LLMs, under review at ICML 2025."
collection: portfolio
---

## Overview

I led the design and implementation of **Geometric Anchor Preference Optimization (GAPO)**, a geometry-aware approach to offline preference learning for large language models. This work bridges geometric stability (inspired by sharpness-aware optimization) and preference-based alignment.

## Motivation

Aligning LLMs with human preferences faces a fundamental tension:

| Approach | Problem |
|----------|---------|
| **Fixed-reference methods** (e.g., DPO) | Static reference becomes miscalibrated as policy drifts, amplifying spurious preference signals under noise |
| **Reference-free methods** (e.g., SimPO) | No explicit stabilizer leads to unconstrained reward drift, harming general capabilities |

GAPO introduces a missing ingredient: **a stabilizer that adapts as the policy evolves**.

## Key Contributions

**Dynamic Geometric Anchor**
- Replaces the fixed reference with an adversarial local perturbation of the current policy within a small l2 radius
- Acts as a pessimistic baseline — if a preference signal remains consistent against this pessimistic neighbor, it reflects robust semantics rather than fragile artifacts

**Anchor Gap & Instance-Wise Reweighting**
- The Anchor Gap measures the reward discrepancy between the policy and its anchor
- Enables automatic geometric filtering: brittle instances (large gap) are downweighted, stable instances (small gap) are emphasized
- Preserves the gradient direction of standard objectives but dynamically scales by instance-dependent weights

**Theoretical Guarantees**
- Proved the Anchor Gap approximates worst-case local margin degradation under smoothness conditions
- Connected to both first-order instability (gradient norm) and second-order sensitivity (Hessian curvature)

## Results

**Instruction-Following (AlpacaEval 2.0 LC Win Rate)**

| Model | DPO | SimPO | GAPO |
|-------|-----|-------|------|
| Mistral-7B | 26.8% | 32.1% | **35.7%** |
| Llama-3-8B | 18.2% | 22.0% | **22.9%** |
| Llama-3-8B-Instruct | 40.3% | 44.7% | **47.4%** |
| Gemma-2-9B | 70.4% | 72.4% | **74.0%** |

**Robustness Under Label Noise (Reward Accuracy)**

| Noise Rate | DPO | Dr.DPO | GAPO |
|------------|-----|--------|------|
| 0% | 63.3 | 66.2 | **66.8** |
| 20% | 62.9 | 64.2 | **64.9** |
| 40% | 57.0 | 58.8 | **59.8** |

**Reasoning Preservation (Alignment Tax)**

GAPO maintained strong reasoning scores (GSM8k: 40.3 on Mistral-7B vs. SimPO's 36.6) while delivering alignment gains, demonstrating reduced alignment tax.

**Hallucination Reduction**

Qualitative analysis showed GAPO produces factually grounded responses where SimPO hallucinates, because factual knowledge resides in geometrically stable regions of the loss landscape.

## Geometric Data Valuation

The Anchor Gap also serves as an implicit data curation signal. Training SimPO on the 30% most stable instances (lowest gap) outperformed both random and unstable subsets, confirming that GAPO's reweighting generalizes beyond the method itself.
