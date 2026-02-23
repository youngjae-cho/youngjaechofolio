---
title: "OCR End-to-End Pipeline for Steel Plate Recognition"
excerpt: "Production OCR system for recognizing steel plate markings with optimized Triton inference and TensorRT acceleration."
collection: portfolio
---

## Overview

Built an end-to-end OCR pipeline for recognizing letters on steel plates in outdoor industrial environments, from detection to recognition to database matching.

## Pipeline Architecture

1. **Object Detection**: Detect areas of interest on steel plates
2. **Character Recognition**: Recognize letters within detected regions
3. **Database Matching**: Match recognized text against existing records

## Optimization

**Latency Analysis & Model Optimization**
- Analyzed Triton inference server logs to identify bottlenecks
- Converted models from ONNX to TensorRT for faster execution
- Implemented warm-up strategies to mitigate cold start latency
- Enabled CUDA graph for further acceleration

**Robustness via Test-Time Augmentation**
- Outdoor conditions introduce noise from weather, lighting, and worker interference
- Developed test-time augmentation strategies within the Triton inference pipeline
- Implemented rotation-aware processing and intelligent padding for robust recognition under varying conditions

## Tech Stack

- **Serving**: Nvidia Triton Inference Server
- **Optimization**: ONNX, TensorRT, CUDA Graph
- **Pipeline**: Python, custom pre/post-processing modules
