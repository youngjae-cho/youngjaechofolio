---
title: "Data Synthesis for Industrial Anomaly Detection"
excerpt: "Diffusion-based pipeline for generating realistic defect samples. F1: 0.30 → 0.67."
collection: portfolio
---

## Summary

Built a diffusion-based synthesis pipeline that generates realistic industrial defect samples and uses them to improve downstream anomaly detection — turning a base F1 of **0.30 into 0.67** with only 200 synthetic samples.

> **Role:** First-author research project at Aiv Co. (preprint in preparation).

## What I Did

- **Background-aware defect generation** — disentangled background and defect representations so the diffusion model preserves substrate texture while editing only the defect region
- **High-resolution training in 24 GB VRAM** — Flash Attention + DeepSpeed ZeRO-2 to fit 2048×2048 training within a single A6000
- **DDIM-based controllable generation** for severity / shape / location of defects, enabling targeted augmentation of long-tail failure modes
- **Validated business impact** on production-like datasets, with detection metrics computed against held-out real defects

## Impact — Detection on Real Defects

| Training set | Precision | Recall | F1 |
|---|---|---|---|
| Base set | 0.63 | 0.20 | 0.30 |
| + 50 synthetic | 0.67 | 0.40 | 0.50 |
| + 200 synthetic | **0.70** | **0.64** | **0.67** |

A 2.2× recall gain at marginal precision cost — translating to **fewer escapes** at the same operator-review budget.

## Stack

PyTorch · Diffusers · Flash Attention 2 · DeepSpeed · OpenCV · Hydra
