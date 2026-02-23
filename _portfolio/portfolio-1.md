---
title: "Data Synthesis for Industrial Anomaly Detection"
excerpt: "Diffusion-based data synthesis pipeline that generates realistic industrial defect samples, boosting detection F1 from 0.30 to 0.67."
collection: portfolio
---

## Overview

Developed a production-ready data synthesis pipeline using diffusion models to generate realistic anomaly samples for industrial inspection tasks. This project bridged the gap between research and deployment, taking a novel diffusion-based method from paper to production.

## Problem

- Anomaly samples are scarce in manufacturing environments, making it difficult to train robust detection models
- Existing generative methods fail to consider the interaction between defects and their backgrounds
- Standard diffusion training requires prohibitive GPU memory for high-resolution (2048x2048) images

## Solutions

**Efficient Training & Inference**
- Replaced inefficient attention operations with Flash Attention across all layers via register functions
- Implemented FP16 mixed-precision training pipeline
- Integrated DeepSpeed for memory-efficient optimization, enabling 2048x2048 training within 24GB VRAM

**Background-Aware Generation**
- Developed disentanglement loss separating background and defect context vectors
- Utilized DDIM Inversion for precise defect placement control
- Implemented masked cross-attention for independent text embedding control

**Demonstrating Business Impact**

| Dataset | Precision | Recall | F1 Score |
|---------|-----------|--------|----------|
| Base set | 0.63 | 0.20 | 0.30 |
| + 50 synthetic images | 0.67 | 0.40 | 0.50 |
| + 200 synthetic images | 0.70 | 0.64 | 0.67 |

## Outcome

Convinced stakeholders with data-driven results, leading to the development of an MLOps platform for end users to leverage synthetic data generation in their workflows.
