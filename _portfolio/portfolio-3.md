---
title: "Bayesian Prompt Learning for Vision-Language Models"
excerpt: "Research on making vision-language prompt learning adaptable through Bayesian modeling with data-dependent priors (AAAI 2024)."
collection: portfolio
---

## Overview

Developed a novel Bayesian framework for vision-language prompt learning that addresses the fundamental challenge of aligning text and image feature spaces in models like CLIP.

## Motivation

Neural network representations between text and image features are not inherently shared. Using text for image retrieval or evaluating text answers using images requires constructing a shared embedding space. Existing prompt learning methods suffer from biased text feature coverage, limiting their generalization.

## Research Questions & Solutions

| Question | Solution |
|----------|----------|
| How to create a common space between image and text features? | Optimize text features to cover the full image feature distribution |
| How to retain CLIP robustness after adaptation? | Adapt text features to unseen image data via data-dependent priors |
| How to train prompts efficiently? | Unconditional prompt learning with Bayesian inference |

## Methodology

- **Bayesian Prior Network**: Models data-dependent priors where context vectors are aware of image feature spaces
- **SVGD Optimization**: Uses Stein Variational Gradient Descent as particle-based variational inference for prompt optimization
- **Test-Time Adaptation**: Adapts context vectors to test inputs via prior maximization, handling distribution shifts

## Results

Achieved strong performance on Base-to-New generalization and ImageNet generalization benchmarks, effectively mitigating the typical performance trade-off between seen and unseen datasets through data-dependent prior adaptation.
