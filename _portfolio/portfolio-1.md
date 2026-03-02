---
title: "Data Synthesis for Industrial Anomaly Detection"
excerpt: "Diffusion-based pipeline for generating realistic defect samples. F1: 0.30 → 0.67."
collection: portfolio
---

## Summary

Built a diffusion-based synthesis pipeline to generate industrial defect samples and improve anomaly detection performance.

## What I Did

- Applied Flash Attention + DeepSpeed for 2048x2048 training within 24GB VRAM
- Added background/defect disentanglement and DDIM-based controllable generation
- Validated business impact on production-like datasets

## Impact

| Dataset | Precision | Recall | F1 |
|---------|-----------|--------|----|
| Base set | 0.63 | 0.20 | 0.30 |
| + 50 synthetic | 0.67 | 0.40 | 0.50 |
| + 200 synthetic | 0.70 | 0.64 | **0.67** |

## Figure Placeholder

> Add image: `/images/portfolio/data-synthesis/overview.png`  
> Recommended content: pipeline diagram (input image, defect control, generated sample).

> Add image: `/images/portfolio/data-synthesis/results-grid.png`  
> Recommended content: generated anomaly examples and detection comparison.
