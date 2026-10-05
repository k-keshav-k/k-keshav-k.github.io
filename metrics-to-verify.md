# Metrics to verify

Every value below is an estimate, not a measured number. In `resume.tex` each one is wrapped in `\est{...}` and renders red in the PDF. Replace a value with your real number, remove the `\est{...}` wrapper, and it prints black again. To clear all marks at once after verifying, redefine the macro:

```latex
\newcommand{\est}[1]{#1}
```

Rebuild with `latexmk -pdf resume.tex`, then copy the PDF over `Keshav Krishna CV.pdf` (or compile `Keshav Krishna CV.tex` directly).

| # | Where | Estimate | What to check |
|---|-------|----------|---------------|
| 1 | Moore Capital | 20+ daily risk/portfolio/ops users | Dashboard access counts, or just ask the team |
| 2 | Moore Capital | VaR/CVaR/beta/correlation runtime cut ~70% | Re-run the Numba benchmark against the original implementation |
| 3 | Moore Capital | Distributed tooling batch throughput ~2x | Cluster scheduler runtimes before vs. after |
| 4 | JioSaavn | 50K+ playlists/day from the LLaMA3 system | Product analytics for that surface |
| 5 | JioSaavn | p95 latency under 2s | Inference monitoring, or reproduce the measurement locally |
| 6 | JioSaavn | Moderation model absorbed ~60% of manual review | Ops numbers: share of items auto-decided after deployment |
| 7 | JioSaavn | 3+ systems owned end to end | Your own count; adjust the number to match |
| 8 | GE Healthcare | 95% detection accuracy | Internship report or your evaluation logs; use the metric you actually measured (mAP, IoU, accuracy) |
| 9 | GE Healthcare | Manual review cut ~80% | Effort before vs. after; if unknown, cut this clause |
| 10 | FlashAttention-2 | 65K-token attention: 10+ GB to under 1 GB | Compute fp16 score-matrix size (tokens² × 2 bytes per head × heads) vs. kernel memory from your run |
| 11 | FlashAttention-2 | Kernels ~2x faster than naive attention | Re-run your benchmark suite and use the measured ratio |
| 12 | Transformer LM | Validation loss 3.1 | Training logs |
| 13 | Transformer LM | Data-pipeline time cut ~3x | Tokenization/loading time with vs. without multiprocessing + mmap |
| 14 | Transformer LM | Best ablation config cut loss ~8% | Your ablation runs; use the val-loss delta of pre-norm + RoPE + SwiGLU vs. baseline |
| 15 | Pico-LLM | Inference throughput ~3x | Benchmark KV-cached/multi-GPU generation vs. naive loop |
| 16 | ML hardware study | 90%+ phase-prediction accuracy | Your predictor eval; if you only measured clustering quality, use that instead |

## Non-numbered claims to sanity-check

- Moore bullet: "before market open" describes the daily risk workflow. Confirm it matches how the reports were actually used.
- "10+ citations" comes from your Sep 23 CV. Re-check Google Scholar before sending.
- Pico-LLM bullet 1 states scope only; bullet 2 carries the metric. Add a result to bullet 1 if you have one.

## Keyword claims to verify

I matched the SLB job posting with generic phrasing, not their product names. SLB-specific names (FM Hub, AI Workspace, Agent Workspace, Delfi, Lumi, GenAI Infrastructure) were left out on purpose: you have not used them, and naming them would be a claim you cannot defend in an interview. What went in instead:

| Phrase added | Where | How to back it up |
|--------------|-------|-------------------|
| "foundation-model systems" | Summary, JioSaavn | LLaMA3-8B work is foundation-model work; keep if you would say it that way in an interview |
| "retrieval-augmented generation" | JioSaavn playlist bullet | The system did retrieval-driven song selection; confirm RAG is a fair label |
| "benchmark dataset, evaluation metrics, acceptance criteria" | JioSaavn moderation | You built the labeled set and picked the model on accuracy; be ready to describe the metrics and cutoff |
| "multi-agent systems, tool-use orchestration, reasoning pipelines" | Skills | Strong claims. Keep only what you can demo or discuss in depth; trim what you cannot |
| "Model Ops (model hubs, versioning, checkpointing)" | Skills, Pico-LLM | Hugging Face + Pico-LLM checkpointing cover this; confirm the wording feels accurate |
| "inference optimization" | JioSaavn, FlashAttention, Skills | Latency/cost work on the playlist system and kernel speedups cover it |
| "cloud AI infrastructure (GCP, Azure)" | Skills | Came from your cloud resume variant; confirm still accurate |
| "domain experts" | JioSaavn cross-functional bullet | Editorial was the music-domain team; fine if that matches how it felt day to day |
| "agentic systems, agent evaluation frameworks" | Skills | Strong claims. Keep only if you have built or evaluated agent behavior and can describe it in depth |
| "continuous evaluation, automated model testing, benchmarking pipelines" | Skills | Your moderation work covers evaluation; keep "continuous" only if those evals ran on an ongoing basis |
| "production-ready GenAI capabilities, scalable service integration" | Skills | Playlist system plus Docker/Kubernetes deployment; confirm the phrasing matches your ownership |
| "compound AI systems" | Skills | LLM + retrieval + product data in the playlist system; keep if you would call it that |
| "developer enablement, technical documentation" | Skills | Only keep if you actually wrote docs or demoed for teammates or stakeholders |
| "GenAI" | Skills heading | Standard label for LLM product work; safe if you are comfortable with it |

Mention `Delfi`, `Lumi`, `geoscience`, `subsurface`, or `reservoir` anywhere only if you have real exposure to them. Right now the resume says nothing about those domains, and that is the honest position.
