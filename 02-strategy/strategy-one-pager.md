# AI Strategy One-Pager - Juno Automated Prioritization

## 1. Problem & Workflow

The Problem: Product discovery at RocketShip is bottlenecked by manual parsing of support tickets, sales calls, and Slack escalations. Roadmap discussions default to the loudest executive voice or latest enterprise escalation rather than verified customer evidence.

Prevention: explicitly prevents 'opinion-driven prioritization' - the bad decision of committing engineering sprints to high-effort features without validating customer pain points, telemetry instrumentation, or technical debt risks.

## 2. Target Metrics

Cycle time: Reduce average weekly roadmap prioritization and PRD drafting time from 10 hours to 1 hour (90% reduction).

Leadership proof: Less than 10% of roadmap decisions reversed within 30 days of sprint kickoff, AND 100% of generated Jira epics have at least 3 verifiable customer citations (Zendesk ticket IDs, Gong timestamps) attached prior to engineering review.

## 3. Autonomy Level

Choice: Semi-autonomous Copilot. The 6-agent squad autonomously ingests data, extracts quotes, and drafts specifications in parallel; a human PM must click 'Push to Jira / Planner' before any work enters an engineering sprint.

Explicitly avoiding: Agent. We will not give the AI autonomous write access to live Jira sprints or customer-facing roadmaps without human review - permitting an AI to commit roadmap dates without human sign-off creates an unacceptable trust-erosion risk.

## 4. Data & Model Approach

Approach: Hybrid (RAG + Agentic). Ground the model in RocketShip's proprietary corpus (Zendesk, Gong, Slack, Notion) to ensure every assertion carries a source citation.

Explicitly avoiding: generic LLM API (Buy). Using a general model without RAG grounding cannot access or cite closed internal systems, which would recreate the loudest-voice problem by hallucinating customer signals that don't exist.

## 5. Risks & Mitigations

Risk: if the AI over-indexes on recent high-ARR escalations, it might systematically ignore critical platform stability or technical debt issues - a one-way door where the roadmap drifts and API latency budgets are violated.

Mitigation: a hard evidence-balance evaluation gate requiring at least 25% of citations to come from structured support tickets rather than ad-hoc Slack threads, plus a required adversarial sign-off from the Lead Engineer agent.

## 6. V1 Scope

In: multi-channel text ingestion, structured pain-point clustering with cited quotes, and automated Version 0.1 PRD drafting with parallel risk/GTM addendums.

Out: (1) autonomous sprint creation or ticket assignment without PM approval, (2) automated customer-facing communications or public release notes.
