---
title: "Make Prompts Adaptable: Bayesian Modeling for Vision-Language Prompt Learning with Data-Dependent Prior"
collection: publications
category: conferences
permalink: /publication/2024-make-prompts-adaptable
excerpt: 'Bayesian prompt learning with data-dependent priors for robust vision-language model adaptation.'
date: 2024-02-01
venue: 'AAAI Conference on Artificial Intelligence (AAAI 2024)'
citation: 'Youngjae Cho, HeeSun Bae, Seungjae Shin, YeoDong Youn, Weonyoung Joo, Il-chul Moon. &quot;Make Prompts Adaptable: Bayesian Modeling for Vision-Language Prompt Learning with Data-Dependent Prior.&quot; <i>AAAI 2024</i>.'
---

Vision-language models like CLIP create shared embedding spaces, but prompt learning methods often suffer from biased text feature coverage. This work introduces a Bayesian framework with data-dependent priors to enable robust prompt adaptation.

**Key Contributions:**
- Introduced a prior network for applying Bayesian priors to prompt learning, enabling mode coverage regularization
- Proposed data-instance-aware context vectors that adapt prompts to individual inputs
- Optimized prompts using Stein Variational Gradient Descent (SVGD) for particle-based variational inference
- Achieved strong performance on Base-to-New generalization and ImageNet generalization benchmarks, mitigating the seen/unseen performance trade-off
