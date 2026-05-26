---
title: "SAAL: Sharpness-Aware Active Learning (ICML 2023)"
excerpt: "Active learning via loss-landscape geometry for efficient data acquisition. Co-first author."
collection: portfolio
header:
  teaser: /images/portfolio/saal/correlation.jpg
---

## Summary

Designed **SAAL**, an active learning method that scores candidate samples by *sharpness* — the worst-case loss in a small parameter neighborhood — instead of uncertainty alone. By preferring informative samples that also induce a flatter loss surface, SAAL bridges Sharpness-Aware Minimization (SAM) and active learning.

> **Status:** Co-first author, published at *ICML 2023*.

## Acquisition Score Is Justified by Geometry

![Loss, gradient norm and 1st Hessian eigenvalue correlate strongly across acquisition iterations.](/images/portfolio/saal/correlation.jpg)

*The proposed acquisition score correlates with three geometric quantities — loss, gradient norm, and the top Hessian eigenvalue — across acquisition iterations. SAAL implicitly minimizes the local Lipschitz / sharpness profile of the model at the selected samples.*

## What I Did

- Derived a **sharpness-based acquisition objective** from worst-case perturbed loss
- Proved a tight connection to the 1st-order curvature of the model — selecting low-sharpness samples drives the learner toward flatter minima
- Validated against six active-learning baselines (Random, Entropy, Coreset, VAAL, BADGE) on Fashion, SVHN, CIFAR-10/100

## Test Accuracy across Benchmarks

![SAAL is at or above every baseline across four benchmarks.](/images/portfolio/saal/accuracy.jpg)

*Test accuracy along the acquisition iteration, trained with SAM optimizers. SAAL (red) matches or exceeds Random / Entropy / Coreset / VAAL / BADGE across all four datasets — gains are largest in low-budget regimes.*

## Loss Landscape Visualization

![3D loss landscapes show SAAL induces flatter minima than uncertainty-based baselines.](/images/portfolio/saal/loss-landscapes.jpg)

*Empirical 3D loss landscapes around the trained models. SAAL's top Hessian eigenvalue $\lambda_1$ is smaller than Entropy and Coreset, confirming flatter minima and better generalization.*
