---
title: "APP: Bayesian Prompt Learning (AAAI 2024)"
excerpt: "Vision-language prompt learning with data-dependent Bayesian priors. First author."
collection: portfolio
header:
  teaser: portfolio/prompt-learning/few-shot.jpg
---

## Summary

Proposed **Adaptive Prior Prompt (APP)**, a Bayesian prompt-learning framework for CLIP-style vision-language models. Instead of learning a single deterministic prompt vector, APP induces a *data-dependent prior* over prompts for every image and learns the posterior variationally — the prompt adapts per input while staying regularized.

> **Status:** First author, published at *AAAI 2024*.

## What I Did

- **Data-dependent Bayesian prior** — replace the shared CoOp prompt with a per-image prior `p(t | x)` parameterized by a small prior network
- **Variational posterior** via Wasserstein-Gradient-Flow / SVGD-based inference — learns the multi-modal structure of text features
- **Repulsive force** between prompt particles to capture diverse semantics of image features
- Improved generalization to **unseen classes** (base-to-new) and out-of-distribution domains

## Few-Shot Classification across 11 Datasets

![APP (red) outperforms CoOp, CoCoOp, PLOT, ProDA across 11 datasets and shot counts.]({{ site.baseurl }}/images/portfolio/prompt-learning/few-shot.jpg)

*APP consistently outperforms CoOp, CoCoOp, PLOT, and ProDA across 11 datasets (Caltech101, DTD, FGVC-Aircraft, Flowers102, Food101, OxfordPets, StanfordCars, SUN397, …). Gains are most pronounced in low-shot regimes.*

## Why It Works — Multi-Modal Prompt Distribution

![UMap visualization showing APP captures multi-modal image feature semantics.]({{ site.baseurl }}/images/portfolio/prompt-learning/umap.jpg)

*UMap visualization of image features and learned text-feature particles on EuroSAT. PLOT and ProDA's text features collapse to a narrow region (top), while APP's particles spread to cover the multi-modal image distribution (bottom). This is the geometric reason APP generalizes to unseen classes.*

## Stack

- **Backbones:** CLIP ViT-B/16, ResNet-50
- **Training:** PyTorch, variational inference, SVGD updates
- **Evaluation:** 11-dataset few-shot benchmark, base-to-new generalization, ImageNet domain shift suite
