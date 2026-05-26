---
title: "OCR End-to-End Pipeline"
excerpt: "Production OCR for outdoor steel-plate recognition. Triton + TensorRT, with TTA-based robustness."
collection: portfolio
---

## Summary

Built and shipped an outdoor steel-plate OCR pipeline — from detection to DB matching — focused on **low latency** and **stable inference** under harsh real-world conditions (rust, low light, motion blur).

> **Role:** ML Research Scientist & Engineer at Aiv Co.

## Pipeline

```
camera feed  →  detector  →  recognizer  →  DB matcher  →  result
                  │             │              │
                  │             │              └─ fuzzy lookup, alias rules
                  │             └─ rotation- / padding-invariant TTA
                  └─ ONNX → TensorRT, CUDA graph, warm-up
```

## What I Did

- **End-to-end flow** — detection → recognition → DB matching, designed as a single Triton-served pipeline
- **Runtime optimization** — ONNX → TensorRT conversion, CUDA Graph capture, and explicit warm-up to stabilize first-batch latency
- **Robustness via test-time augmentation** — rotation and padding TTA reduced misreads on rotated/cropped plates without retraining
- **Operations** — health-checked deployment with versioned model registry and a small offline replay tool for regression catching

## Stack

NVIDIA Triton Inference Server · TensorRT · ONNX Runtime · CUDA Graphs · Python · Docker
