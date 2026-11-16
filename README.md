# Hybrid quality agent

Personal **reference copy** of a keyword-first hybrid quality agent: intent router, handlers, suite catalog, and rule RCA.

This is a portfolio / interview reference snapshot. It is **not a company product** and not affiliated branding as a product SKU. There are no employer internals, no live tenants, and no personal access tokens in this tree.

The public GitHub Pages lab is a separate demo (console, Allure HTML, GaussIQ dummy-tenant files). Those files are not in this repository. You do not need them to run the agent.

## What it is

The router is keyword / rule based. The first matching rule wins. Numbers always come from:

- handlers reading `agent/fixtures/`
- cited knowledge-base files under `agent/kb/`
- the suite catalog in `agent/fixtures/suites.json`

A language model is **optional rephrase only**. This sample ships with the model off (`agent/summarizer.py`). A model does not pick tools, invent metrics, or set RCA.

## Run locally

```bash
git clone https://github.com/sanket-dhamke/HybridQualityAgent.git
cd HybridQualityAgent
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
pytest
```

CLI:

```bash
python -m agent "Which pods are crashing or restarting after OOM?"
```

Lab login in fixtures is fictional `emuser` / `empass`. Charts, asset counts, and ingest runs are simulated.

## Layout

- `agent/` — router, handlers, RCA engine, security engine, KB, recipes, fixtures
- `tests/` — pytest for routing, RCA, security, and app health
- `requirements.txt` — pytest

## Honesty

Chat suite results replay `agent/fixtures/suites.json` (same smoke / sanity / regression markers). They are catalog reads, not a live pytest spawn.
