# AI Content Orchestrator

An automated system that generates, validates, and publishes Instagram content — where the final decision always stays with a human.

The topic is intentional: psychology and neuroscience. A domain where AI cannot simply generate — it has to classify, filter, verify sources, and follow strict safety rules. This makes it a good test environment for the real question:

**Can an AI agent work autonomously, complete tasks correctly — and still remain under control?**

## What it does

The system takes a topic, researches scientific sources, verifies their credibility and quality, writes a post, checks it for safety and quality, and presents it for human approval. Nothing gets published without explicit sign-off.

Topic → Classify → Research → Verify sources → Generate → Validate → Human Gate → Publish

## Key principles

A prompt asks. Code enforces.

Every hard rule lives in deterministic code — not in prompts. The system cannot override them. Human approval is not optional — it is hardcoded.

Don't make the system smarter. Make it more observable and controllable.

## What's built — Day 40

- Safety classifier — GREEN / YELLOW / RED zones with CONFIDENCE levels
- Policy Layer — all rules in deterministic code, not prompts
- Validator — safety, format and quality checks, up to 3 retry attempts
- Human Gate — web interface for structured human approval
- PostgreSQL — posts, validation logs, decisions, failure patterns
- Memory Layer — system learns from past failures by topic and error type
- Observability dashboard — 6 real-time metrics
- Threshold Alerts — daily automated health check
- Versioning — prompt versions and change log

## Stack

- Orchestration: n8n (self-hosted)
- AI: Claude API — Haiku (classification) + Sonnet (generation)
- Search: Perplexity API
- Database: PostgreSQL 16
- Server: Hetzner VPS, Nuremberg EU (~23 EUR/month)
- Queue: Google Sheets

## Architecture

![Pipeline](assets/canvasa_.png)

## Status

Active development. Day 40. First posts published. All P0 safety tests passed.

Building toward full Autonomy Governance Layer (AGL) and EU AI Act compliance.

*Natalia Chernenkaya · Prague · 2026*
