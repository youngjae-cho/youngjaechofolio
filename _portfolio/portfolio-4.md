---
title: "Sharpness-Aware Active Learning (SAAL)"
excerpt: "Novel active learning method using flat minima theory for efficient data acquisition (ICML 2023)."
collection: portfolio
---

## Overview

Proposed Sharpness-Aware Active Learning (SAAL), a principled active learning framework that leverages loss landscape geometry to select the most informative samples for labeling.

## Motivation

Active learning aims to minimize labeling costs by selecting the most informative data points. Traditional acquisition functions lack theoretical grounding in generalization theory. We derived a connection between active learning and loss landscape sharpness.

## Methodology

**Generalization Bound**

We established a generalization bound decomposition showing that the population loss can be bounded by components related to labeled data, unlabeled data, and the sharpness of the loss landscape.

**Acquisition Function**

SAAL uses the maximally perturbed loss as the acquisition score:

*f_acq(x; model) = max_{perturbation} loss(x, y; theta + perturbation)*

This selects samples where the model's predictions are most sensitive to parameter perturbations — indicating regions where more data would most improve generalization.

## Results

SAAL achieves state-of-the-art performance across standard active learning benchmarks by efficiently identifying samples that contribute most to learning flat, generalizable minima.
