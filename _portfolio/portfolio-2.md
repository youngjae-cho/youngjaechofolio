---
title: "OCR End-to-End Pipeline"
excerpt: "Production OCR for steel plate recognition with Triton serving and TensorRT optimization."
collection: portfolio
---

## Summary

Developed an outdoor steel-plate OCR pipeline from detection to DB matching, with a focus on low latency and stable inference.

## What I Did

- Built end-to-end flow: detection → recognition → DB matching
- Optimized runtime with ONNX→TensorRT conversion, CUDA graph, and warm-up
- Improved robustness using test-time augmentation (rotation, padding)

**Stack**: Triton Inference Server, TensorRT, ONNX, Python

## Figure Placeholder

> Add image: `/images/portfolio/ocr/pipeline.png`  
> Recommended content: full OCR system architecture.

> Add image: `/images/portfolio/ocr/latency-comparison.png`  
> Recommended content: before/after latency chart.
