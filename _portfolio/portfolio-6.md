---
title: "LLM Benchmarking CLI"
excerpt: "Unified benchmarking tool for LLM inference performance and pipeline stability."
collection: portfolio
---

## Summary

Built a unified CLI for LLM inference benchmarking across throughput, serving load, and end-to-end scenarios.

## What I Did

- Implemented pluggable engine adapters (vLLM, Hugging Face, synthetic fallback)
- Built async load generation with latency/error/token-throughput metrics
- Added JSON/CSV reports and CI-friendly pass/fail gate output

**Stack**: Python, Typer, httpx (async), Pydantic, pytest, Rich

## Figure Placeholder

> Add image: `/images/portfolio/mantis-bench/architecture.png`  
> Recommended content: CLI architecture and adapter structure.

> Add image: `/images/portfolio/mantis-bench/report-example.png`  
> Recommended content: sample benchmark output/report screenshot.
