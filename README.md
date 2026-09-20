# Juno: AI Copilot for Automated Ticket Triage & Routing

> An autonomous AI workflow that ingests Zendesk support signals, evaluates them against strategic priorities, and automatically routes P1 product risks for immediate triage.

_R.J. Rimando · AI PM Cohort · September 2026_

Repo: https://github.com/MindForNumbers/juno-pm-copilot

This repo is my final project for the AI Product Management Certification — **Juno: AI Copilot for Automated Ticket Triage & Routing**. Each module’s artefact lives in its own folder; this README is the dashboard and the pitch.

---

## Module artefacts

### M1 · Prompting
- **System prompt** — [`01-prompting/skill-file.md`](01-prompting/skill-file.md)
- **Prototype** — https://juno-pm.lovable.app

### M2 · Strategy
- **Decision matrix** — [`02-strategy/decision-matrix.md`](02-strategy/decision-matrix.md)
- **AI Strategy one-pager** — [`02-strategy/strategy-one-pager.md`](02-strategy/strategy-one-pager.md)

### M3 · RAG / AI PRD
- **AI PRD** — [`03-harness-prd/prd.md`](03-harness-prd/prd.md)

### M4 · AI-Native UX
- **AI user flow** — [`04-ai-ux/user-flow.md`](04-ai-ux/user-flow.md)
- **Trust-gap mitigations** — [`04-ai-ux/trust-gaps.md`](04-ai-ux/trust-gaps.md)

### M5 · Agentic Workflows
- **Agent Workflow Spec (AWSpec)** — [`05-agentic-workflows/awspec.md`](05-agentic-workflows/awspec.md)
- **Agent Control Panel** — [`05-agentic-workflows/agent-control-panel.md`](05-agentic-workflows/agent-control-panel.md)

### M6 · Evals &amp; Guardrails
- **Eval stack** — [`06-evals/eval-stack.md`](06-evals/eval-stack.md)
- **Human evaluation rubric** — [`06-evals/human-rubric.md`](06-evals/human-rubric.md)

---

## PM Execution Plan

### Where Juno is today
The M1 Langflow prototype is fully architected and visually validates the multi-agent routing flow.   
The logic gate successfully processes Zendesk P1 test signals, extracting quotes and outputting verified JSON payloads (STATUS_APPROVED).   
Vector storage (Chroma DB) and embeddings (HuggingFace) are mapped but currently running in a "Wizard of Oz" bypass due to external network constraints.

### What ships next (next 2 sprints)
Sprint 1: Resolve the SSRF network constraints to fully integrate the HuggingFace embedding pipeline with Chroma DB for live strategy retrieval.
Sprint 2: Wire the Langflow Chat Output directly into a Slack webhook to push JSON triage alerts into a live PM channel, and launch a closed alpha with 2 Product Managers.

### What I watch (dashboards)
Daily: False-positive routing rate (P3 tickets escalated as P1), pipeline execution latency (target < 10 seconds), and LLM API failure rates.
Weekly: Average token usage/cost per execution, successful extraction rate of verbatim customer quotes, and total hours saved on manual Zendesk triage.

### Red lines (what blocks shipping)
< 95% routing accuracy against our standardized P1 golden-set test data. 
Any hallucination or modification of direct customer quotes within the JSON payload. 
Langflow execution timeouts exceeding 15 seconds, creating unacceptable latency for live support handoffs.

### Governance
Compliance: Enforce strict PII scrubbing on all incoming Zendesk/Gong transcripts prior to vector storage to maintain SOC2 and GDPR alignment.

Safety: Guardrails against prompt injection originating from customer ticket text; Juno must remain strictly internal-facing with no automated replies sent to users.

Reliability: Establish fallback routing logic to immediately push signals to a manual PM triage queue if the Langflow/Gemini API times out or fails.

Reputation: Maintain complete audit logs of all generated JSON routing decisions to ensure accountability if an Enterprise-tier P1 risk is ever misclassified.

---

## Build Insights

- **Friction point.** Network SSRF constraints and API version mismatches completely blocked our vector embeddings, requiring a "Wizard of Oz" hardcoded context bypass to unblock and test the core routing logic.
- **Key learning.** Probabilistic models require deterministic guardrails. Enforcing a strict JSON schema and specific output strings (like STATUS_APPROVED) was mandatory to make the Langflow If-Else routing gate function reliably.
- **Aha moment.** The AI isn't the product; the routing logic is. Structuring the prompt to act purely as a data translation layer allows you to treat LLMs like standard API endpoints in a larger software workflow.

---

_Certification submission — AI Product Management Certification._
