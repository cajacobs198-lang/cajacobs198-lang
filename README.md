## Hi, I'm Chaim 👋

I build GTM engineering systems — the infrastructure that sits between a company's data warehouse, its CRM, and the humans on its revenue team. The repos pinned below are a portfolio. Each one solves a real problem I've watched RevOps and sales teams struggle with, and each is shipped as a working, runnable codebase with tests, CI, and "why this design" written down.

If you're hiring for a GTM engineering role and want to skim 90 seconds of work, start with **lead-enrichment-pipeline** or **warehouse-to-crm-rev-etl**.

---

### 📦 Portfolio

#### Lead enrichment & scoring
- **[lead-enrichment-pipeline](https://github.com/cajacobs198-lang/lead-enrichment-pipeline)** — Async multi-provider enrichment (Clearbit + Apollo + PDL), normalized canonical schema with full provenance, dedupe, persistence. *FastAPI · Celery · Postgres · Redis.*
- **[ai-lead-scoring](https://github.com/cajacobs198-lang/ai-lead-scoring)** — Hybrid rules + Claude classifier. YAML rules for the deterministic part, LLM for the judgment part. Every score comes back with per-signal explanations.
- **[icp-finder](https://github.com/cajacobs198-lang/icp-finder)** — Five seed customers in, 100 ranked lookalikes out. Embeddings + cosine + optional LLM re-rank. Ships with a runnable dataset.

#### CRM automation
- **[hubspot-sync-engine](https://github.com/cajacobs198-lang/hubspot-sync-engine)** — Bidirectional Postgres ↔ HubSpot custom-object sync. Webhook listener, four conflict-resolution policies, idempotent writes, full audit log.
- **[salesforce-dedupe-merge](https://github.com/cajacobs198-lang/salesforce-dedupe-merge)** — Fuzzy-match dedupe with rapidfuzz blocking + LLM tiebreaker. Dry-run mode + audit log so RevOps can sign off before merges hit production.

#### Outbound
- **[personalized-outbound-engine](https://github.com/cajacobs198-lang/personalized-outbound-engine)** — Per-prospect cold emails. Pulls research signals, generates 3 variants per prospect, refuses to write generic pablum if research is empty.
- **[deliverability-monitor](https://github.com/cajacobs198-lang/deliverability-monitor)** — Inbox placement tracker. Sends seeds through SendGrid/Postmark, polls Gmail/Outlook, alerts when (esp × sending domain × mailbox provider) inbox rate drops.

#### AI agents · reverse ETL · analytics
- **[meeting-prep-agent](https://github.com/cajacobs198-lang/meeting-prep-agent)** — Pre-call research agent. LangGraph + tool use. Produces a one-page markdown brief with company news, funding, jobs, competitive framing, and three suggested talk tracks. Includes ADR.
- **[warehouse-to-crm-rev-etl](https://github.com/cajacobs198-lang/warehouse-to-crm-rev-etl)** — Reverse-ETL framework with YAML model files. Incremental sync, schema drift detection, sync state in your own Postgres. Includes ADR on build-vs-buy.
- **[attribution-modeling-toolkit](https://github.com/cajacobs198-lang/attribution-modeling-toolkit)** — First-touch, last-touch, linear, time-decay, and Markov-chain attribution — implemented from first principles, side-by-side comparable in a Streamlit dashboard.

---

### How to read these

Every repo has the same structure: a `README.md` that names the GTM problem first, an architecture diagram, a `Quick start` you can run in two commands (most use mock providers/fixtures so they work without API keys), and tests under `tests/`. The two repos with formal trade-off docs (`meeting-prep-agent`, `warehouse-to-crm-rev-etl`) include an ADR in `docs/`.

### Stack

Python-first: FastAPI, Celery, SQLAlchemy, pandas, pydantic, LangGraph, Anthropic SDK. Postgres for state. Docker compose where it earns its keep.

### Reach out

[📧 data@qualifier.co](mailto:data@qualifier.co)
