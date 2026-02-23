---
title: "Background-Aware Defect Generation for Robust Industrial Anomaly Detection"
collection: publications
category: manuscripts
permalink: /publication/2025-background-aware-defect-generation
excerpt: 'A diffusion-based framework that disentangles background and defect contexts to generate realistic anomaly samples for industrial inspection.'
date: 2025-01-01
venue: 'Preprint'
citation: 'Youngjae Cho, Gwangyeol Kim, Sirojbek Safarov, Seongdeok Bang, Jaewoo Park. &quot;Background-Aware Defect Generation for Robust Industrial Anomaly Detection.&quot; <i>Preprint</i>.'
---

In industrial anomaly detection, anomaly samples are insufficient to train robust models. In real manufacturing scenarios, it is difficult to obtain certain defect types. This work proposes synthesizing anomaly samples using diffusion models while considering the interaction between defects and their backgrounds.

**Key Contributions:**
- Proposed a disentanglement loss that separates background and defect context vectors, ensuring the background is not affected by defect generation
- Utilized DDIM Inversion to effectively control defect placement on target latent representations
- Introduced masked cross-attention mechanisms to disentangle text embeddings for controllable generation
- Demonstrated superior generation quality (FID, LPIPS) over baselines and significant downstream detection performance gains
