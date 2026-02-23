---
title: "mantis-bench: Unified LLM Benchmarking CLI"
excerpt: "A unified benchmarking package for measuring model inference performance and pipeline stability across throughput, serving load, and end-to-end scenarios."
collection: portfolio
---

## Overview

Designed and implemented **mantis-bench**, an integrated benchmarking package that standardizes throughput (QPS/latency), serving stress tests, and end-to-end pipeline stability under a single CLI interface.

## Architecture

**Pluggable Engine Abstraction**
- Built a protocol-based engine adapter layer supporting multiple backends: vLLM, Hugging Face Transformers, and a synthetic engine fallback
- The synthetic fallback enables reliable CI testing and reproducible benchmarking in GPU-less environments
- Clean protocol-based design allows adding new engine backends with minimal code changes

**Async Load Generation & Metric Aggregation**
- Implemented asynchronous load generation using httpx for realistic serving stress tests
- Comprehensive metric aggregation: latency percentiles (p50/p95/p99), error rates, token throughput (tokens/sec), and QPS
- Supports multiple benchmark scenarios in a single run: throughput measurement, serving load simulation, and end-to-end pipeline validation

**Automated Reporting & Regression Tracking**
- Multi-format artifact generation: JSON, CSV, and Rich terminal tables
- Release-gate style pass/fail summaries for automated regression tracking
- Designed for integration into CI/CD pipelines to catch performance regressions before deployment

## Tech Stack

| Category | Tools |
|----------|-------|
| **Core** | Python, Typer, Pydantic, dataclasses |
| **Async / Networking** | httpx (async), asyncio |
| **Data & Reporting** | NumPy, PyYAML, Rich |
| **Testing & Quality** | pytest, ruff |
| **GPU / Serving** | PyTorch, vLLM, Hugging Face Transformers, Locust (optional) |
