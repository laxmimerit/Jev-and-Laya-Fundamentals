# Jev and Laya Fundamentals: Decision AI for Beginners

A KGP Talkie course on Jev, TypeSafe AI's System One model, and the decision models that followed it. A decision model reads a state (text or JSON) plus typed questions (`choice`, `score`, `noul`) and returns typed answers with probabilities in one pass. It never writes text.

| Section | Topic | Use case |
|---|---|---|
| 1 | Support ticket triage: raw HTTP and the SDK, writing good questions, confidence worked out, JSON state, typed results, async, retries, cost | 40 SaaS support tickets, triage table with a confidence gate |
| 2 | Product review dashboard: questions as columns, fan-out, dashboards, composite scoring | Product review dashboard, sales lead scoring |
| 3 | Bank message router, testing before launch: accuracy, misses, calibration, thresholds, failure modes, version pinning | 200 real Banking77 card messages |
| 4 | Laya on your machine with Ollaya | Inbox routing, feedback in Hindi, Hinglish, Tamil and Bengali |
| 5 | Ollama's decision endpoint and nimble | Checking outbound messages for personal data |
| 6 | Jev-like APIs across providers: OpenRouter, Liquid, Perplexity, Cloudflare, OpenAI's preview, llama.cpp and more | One routing question, every backend |

Each section has two files with the same name:

- `slides/NN_*.pdf` is the deck. All the explanation lives here.
- `notebooks/NN_*.ipynb` is the code. Data is in `notebooks/data/` as CSV.
- Run the notebooks from the `notebooks/` folder.

## Setup

You need Python 3.12 and [uv](https://docs.astral.sh/uv/).

```bash
uv sync
```

```bash
cp .env.example .env
```

Put one OpenRouter key in `.env` as both `OPENROUTER_API_KEY` and `TYPESAFE_API_KEY`. The TypeSafe SDK reaches Jev through `TYPESAFE_BASE_URL=https://openrouter.ai/api`. A key from the TypeSafe console works too, with `TYPESAFE_BASE_URL=https://api.typesafe.ai`.

On Windows, set `PYTHONUTF8=1` before starting Jupyter, so the `!ollaya` and `!ollama` cells print their bars and arrows correctly.

## Local Servers

### Ollaya on port 11435, for Sections 4 and 6

Windows (PowerShell):

```powershell
irm https://ollaya.dev/install.ps1 | iex
```

Linux and macOS:

```bash
curl -fsSL https://ollaya.dev/install.sh | sh
```

```bash
ollaya pull laya
```

### Ollama 0.35 or later on port 11434, for Sections 5 and 6

Install from [ollama.com](https://ollama.com), then:

```bash
ollama pull nimble
```

```bash
ollama pull tev1:0.8b
```
