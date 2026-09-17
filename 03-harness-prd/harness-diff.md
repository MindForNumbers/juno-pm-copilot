## Diagnostic Diff · Juno RAG Lab

_Working notes from Module 3 Lab 1. Do not paste over `03-rag-prd/prd.md`. That file comes from the AI PRD Builder._

**Prototype:** https://product-mind-fusion.lovable.app

### Before - Quality Mode (no strategy)

Rank	Priority	Signal	Owner	Score
1	P1	CSV export crashes after prolonged loading	Synthesizer	88
2	P2	CSV export has no actionable failure state	Drafter	75
3	P2	CSV export lacks measurable reliability telemetry Data Scientist 69

### After - Strategy Mode (with RocketShip Strategy One-Pager)

Rank	Priority	Signal	Owner	Score
1	P0	CSV export crashes after prolonged processing	Synthesizer	100
2	P1	CSV export latency violates speed-to-insight	Data Scientist	95
3	P1	Export failure has no actionable error state	Drafter	90

### Takeaway

> Strategy document grounded Juno to make logical and precise priorities.
