---
title: "LLM Benchmarking CLI"
excerpt: "Unified CLI for LLM inference performance, serving load, and pipeline-stability benchmarks. CI-friendly."
collection: portfolio
---

## Summary

Built a unified command-line tool for benchmarking LLM inference across **throughput**, **serving load**, and **end-to-end stability** scenarios. Designed to be both a research microscope and a CI gate — produces JSON/CSV reports and exits non-zero when latency or error budgets are blown.

## What I Did

- **Pluggable engine adapters** — vLLM, Hugging Face TGI / native, and a synthetic fallback engine for shaping load without a real model
- **Async load generation** — `httpx`-based concurrent client with configurable QPS profiles, recording per-request latency, error, and token-throughput metrics
- **Reports** — JSON for downstream tooling, CSV for spreadsheets, and a colored Rich-rendered summary on stdout
- **CI-friendly gates** — `--p95-latency-budget`, `--error-budget`, `--min-throughput` flags so a benchmark can fail a pipeline like any other test
- **Typed and tested** — Pydantic configs, pytest suite, and reproducible runs via seeded synthetic fallback

## Example

```bash
mantis-bench run \
  --engine vllm --base-url http://localhost:8000 \
  --model meta-llama/Llama-3-8B-Instruct \
  --workload chat-mixed --duration 60s --qps 32 \
  --p95-latency-budget 1200ms --error-budget 0.5% \
  --report-json out/run.json
```

## Stack

Python · Typer · httpx (async) · Pydantic · pytest · Rich
