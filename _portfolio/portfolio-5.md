---
title: "GAPO: Geometric Anchor Preference Optimization"
excerpt: "Geometry-aware preference alignment for LLMs. First-author, under review at NeurIPS 2026."
collection: portfolio
header:
  teaser: portfolio/gapo/concept.jpg
---

## Summary

Proposed **GAPO**, a geometry-aware preference optimization method for robust LLM alignment. GAPO replaces the static reference of DPO (and the reference-free margin of SimPO) with a *dynamic adversarial anchor* — a small worst-case perturbation of the current policy — and reweights each preference pair by its local geometric brittleness.

> **Status:** First author, under review at NeurIPS 2026.

## The Idea

![DPO vs SimPO vs GAPO: a moving anchor that tracks the policy and reweights brittle pairs.]({{ site.baseurl }}/images/portfolio/gapo/concept.jpg)

*DPO uses a frozen reference (distributional mismatch as the policy drifts). SimPO has no anchor (unconstrained drift). GAPO's dynamic anchor tracks the policy and assigns smaller updates to brittle pairs.*

## What I Did

- **Dynamic Geometric Anchor** — adversarial perturbation of model parameters within an L2 ball, acting as a pessimistic local surrogate that adapts as the policy evolves
- **Anchor Gap reweighting** — instance-wise weights that downweight geometrically brittle preferences without modifying the gradient direction
- **Theoretical analysis** — proved the Anchor Gap approximates worst-case local margin degradation under smoothness, connecting it to local sharpness and margin sensitivity
- **Empirical validation** across four open-weight backbones (Mistral-7B, Llama-3-8B Base/Instruct, Gemma-2-9B) on AlpacaEval 2.0 and Arena-Hard

## Key Result — AlpacaEval 2.0 LC Win Rate

| Model | DPO | SimPO | **GAPO** |
|-------|-----|-------|------|
| Mistral-7B Instruct | 26.8% | 32.1% | **35.7%** |
| Llama-3-8B Base | 18.2% | 22.0% | **25.0%** |
| Llama-3-8B Instruct | 40.3% | 44.7% | **47.4%** |
| Gemma-2-9B | 70.4% | 72.4% | **74.0%** |

## Robustness to Label Noise

![Reward accuracy stays high under both random and length-dependent label flips.]({{ site.baseurl }}/images/portfolio/gapo/robustness.jpg)

*GAPO degrades smoothly under both random and length-dependent label flips — Dr.DPO collapses below DPO past 20% flip rate. No explicit noise model is needed.*

## Diagnostic — Anchor Gap Identifies Brittle Pairs

![Flipped preferences receive systematically smaller GAPO weights.]({{ site.baseurl }}/images/portfolio/gapo/anchor-gap.jpg)

*Mean GAPO weight on flipped pairs falls **16.9%** below clean pairs by end of the first epoch (left). Stratified by weight tier, the bottom-20% slice over-represents noisy preferences by **+13.1 pp** vs the top-20% (right).*

## Compute Efficiency

![1 epoch of GAPO beats 2 epochs of SimPO at the same wall-clock budget.]({{ site.baseurl }}/images/portfolio/gapo/wallclock.jpg)

*At matched wall-clock budget, GAPO delivers **+3.6 pp** over an extended SimPO run on Mistral-7B Instruct.*
