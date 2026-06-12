# Jaden Bryan

**PM + Infrastructure Engineer** building compute and AI inference platforms — from PRD to production deployment.

I ship the kind of products I can also build myself: AI inference runtimes, distributed systems, and the observability that keeps them honest. I write rigorous specs, own customer integrations end-to-end, and treat documentation as a first-class deliverable.

📍 Seattle, WA · [LinkedIn](https://linkedin.com/in/jaden-bryan) · [Email](mailto:jaden@bryan.fund)

---

## What I Do

| | |
|---|---|
| **AI Inference Infra** | vLLM · llama.cpp · ROCm/CUDA · OpenAI-compatible serving · flash attention · quantization (AWQ, GGUF) |
| **Product Management** | PRD authorship · acceptance criteria · roadmap ownership · launch readiness · compatibility matrices · GTM |
| **Distributed Systems** | edge orchestration · adaptive rate control · backpressure · idempotent ingestion · resumable jobs |
| **Cloud & Tooling** | Azure · Cloudflare Workers · Docker · Kubernetes · SQLite/Postgres · Python (PyTorch, pandas) |

---

## Featured Projects

### 🔧 [Layered AI Inference Stack — *AMD MI50 / gfx906*](https://github.com/bryan-fund/ML-gfx906)
A reproducible inference runtime for unsupported accelerator hardware, packaged so others can run it without owning the upstream stack.

- Built a layered deployment path: **ROCm → PyTorch → vLLM / llama.cpp**, patching and version-pinning ROCm for unsupported gfx906 GPUs
- Ships as a **Docker Compose artifact** serving an OpenAI-compatible endpoint — full GPU offload, 32k context, flash attention, env-driven tensor-split for multi-GPU vs single-GPU fallback
- Authored a full **compatibility matrix**: engine benchmarks, supported feature sets, thermal and quantization tradeoffs
- Designed a distributed observability layer: token-bucket rate limiting, EMA latency tracking, and a React dashboard for live runtime and per-worker metrics

> **Proves:** I can take frontier-but-unsupported hardware to a production-style, documented, reproducible runtime.

### 🌐 [Distributed Property Data Platform](https://github.com/bryan-fund/worker-scraper)
A multi-worker scraping and ingestion system with adaptive throttling and first-class observability.

- Orchestrates **parallel Cloudflare Workers** with a two-level buffering model (global pool + per-worker queue)
- **Adaptive throughput control**: token-bucket limiter with dynamic refill, EMA latency tracking, HTTP 520 detection, and safe-mode backoff that trades raw rate for upstream stability
- **Resumable + idempotent**: progress derived from DB state, `INSERT OR REPLACE` writes, restartable workers
- **React + TypeScript dashboard** polling collector APIs for progress, worker health, throughput, and utilization vs theoretical max

> **Proves:** distributed systems design — backpressure, fault tolerance, and operator-facing observability.
>
> *Scope: targets public assessor data with built-in throttling and error backoff; built as a systems demonstration.*

### 🤖 [Agent Verse — Multi-Agent Systems](https://github.com/bryan-fund/agent-verse)
A personal sandbox (built on OpenBMB's AgentVerse) for designing and running LLM agent systems.

- Multi-agent orchestration with configurable roles, memories, prompts, parsers, and environment rules
- A **village economy simulation** where agents farm, trade, negotiate, take loans, and vote
- **FastAPI** backend for simulation control and world state; local + remote model backends via **vLLM** and OpenAI-compatible APIs
- Structured output parsing that constrains model output into executable JSON actions

> **Proves:** agentic orchestration, prompt engineering, and model-backend integration.

### 🔐 [Hardware-Backed Authentication](https://github.com/bryan-fund/hardware-auth-portfolio)
End-to-end secure auth across firmware and web layers.

- Fingerprint presence verification on **ESP8266** + **ECDSA P-256** signing via ECC608 secure element
- Next.js endpoint proxying with client-side signature verification (`@noble/curves`)
- Full visibility into auth state, signature material, and verification results

> **Proves:** device-to-web integration and cryptographic verification.

### 🖥️ [PiKVM Visual-Language MCP](https://github.com/bryan-fund/automator-portfolio)
A self-contained **MCP server** for automating and inspecting a remote machine via PiKVM.

- Screen-capture, visual analysis, and HID control wrapped as MCP tools
- Grounded coordinate output for UI-directed actions; optional external model hooks

> **Proves:** MCP tooling and practical agent-driven automation.

---

## Education

**UC Berkeley** · B.A. Data Science + B.S. Business Administration (Haas) · 2020–2024
President, CMG Strategy Consulting Club · 2nd Place, Gates Foundation Case Competition
