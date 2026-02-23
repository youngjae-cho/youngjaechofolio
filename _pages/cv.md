---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* **M.S. in Industrial & Systems Engineering**, KAIST, 2022 – 2024
  * Focus: Machine Learning, Bayesian Modeling, Multi-modal Learning
  * Advisor: Professor Il-Chul Moon
* **B.S. in Industrial & Systems Engineering**, KAIST, 2017 – 2022
  * Focus: Statistics, Optimization, Machine Learning

Work Experience
======
* **ML Research Scientist**, Pyler (Oct 2025 – Present)
  * Alternative military service
  * Led first-author research on GAPO, a geometry-aware preference alignment method for LLMs (under review at ICML 2025)
  * Designed and implemented mantis-bench, a unified benchmarking CLI for model inference performance and pipeline stability (throughput / serving load / end-to-end)
  * Built a protocol-based engine abstraction supporting vLLM, Hugging Face, and synthetic fallback for GPU-less CI testing
  * Implemented async load generation with metric aggregation (percentiles, error rates, token throughput) and automated pass/fail gate reports

* **ML Research Scientist**, Aiv Co. (Mar 2024 – Oct 2025)
  * Alternative military service
  * Developed data synthesis pipeline using diffusion models for industrial anomaly detection
  * Built OCR end-to-end pipeline for steel plate letter recognition
  * Optimized training and inference with Flash Attention, DeepSpeed, and TensorRT
  * Developed MLOps platform for data synthesis service

Skills
======
* **Machine Learning Frameworks**: PyTorch, TensorFlow, JAX, Scikit-Learn
* **LLM Serving & Inference**: vLLM, Hugging Face Transformers
* **Model Optimization**: ONNX, TensorRT, Flash Attention, DeepSpeed
* **Serving & Infrastructure**: Nvidia Triton Server, MLOps Pipeline
* **Benchmarking & Testing**: Typer, httpx (async), Pydantic, pytest, Locust
* **Python Tooling**: NumPy, PyYAML, Rich, ruff
* **Research Areas**: Bayesian Modeling, Generative Models, Active Learning, Multi-modal Learning, Anomaly Detection, LLM Preference Alignment

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Service and Leadership
======
* Academic Counseling Assistant, Department of Industrial & Systems Engineering, KAIST
