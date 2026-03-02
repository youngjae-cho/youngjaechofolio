---
title: "GAPO: Geometric Anchor Preference Optimization"
excerpt: "Geometry-aware preference alignment for LLMs. First-author, under review."
collection: portfolio
---

## Summary

Proposed GAPO, a geometry-aware preference optimization method for robust LLM alignment.

## What I Did

- Replaced fixed references with dynamic geometric anchors
- Introduced Anchor Gap-based instance reweighting
- Improved instruction-following metrics on multiple base models

## Key Result

| Model | DPO | SimPO | GAPO |
|-------|-----|-------|------|
| Mistral-7B | 26.8% | 32.1% | **35.7%** |
| Llama-3-8B-Inst | 40.3% | 44.7% | **47.4%** |
| Gemma-2-9B | 70.4% | 72.4% | **74.0%** |

*AlpacaEval 2.0 LC Win Rate*

## Figure Placeholder
