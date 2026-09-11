# T5 — Trustworthy AgentOps: Supply Chain & Procurement

**Course:** CS 4485.0W1 — Fall 2026
**Faculty Advisor:** Prof. Dr. Sadi Evren Seker (Sadi.Seker@UTDallas.edu)
**Team:** T5 | Tuesday slot: 1:30–1:45 PM CT
**Application Vertical:** Supply chain and procurement — spend limits, supplier eligibility, contract terms

## Team

| Name | UTD Email | Role (Week 1) |
|---|---|---|
| Jay Trivedi | jht230000@utdallas.edu | Team Leader (rotates weekly) |
| Zakarias Zewdu | zxz210018@utdallas.edu | | 
| Neha Senthil-Kumar | nxs220105@utdallas.edu | | Time Keeper
| Hafa Kazi | nsk210004@utdallas.edu | |
| Zach Johnson | zmj230000@utdallas.edu | |
| Jared Lillie | jjl220004@utdallas.edu | | Scribe


## Problem

Multi-agent AI workflows call models, tools, APIs, and other agents. When something fails, there's no single timeline, failures are silent, and no one owns the decision to approve, reject, or stop an action. This system exists to answer four questions for every run: **What happened? Why did it happen? Who approved it? Can we undo it?**

## What We're Building

Core objectives (MVP — all required):
1. **Ingest** — accept agent-run events (JSON files + simple API), validated against a versioned schema
2. **Visualize** — trace view of agents, models, tool calls, cost, latency, status
3. **Detect** — identify policy violations against T5's procurement rules, with an explanation per violation
4. **Review** — human-in-the-loop: approve / reject / stop / simulated rollback
5. **Audit** — searchable, append-only trail of every run and human decision

**Success metrics:**
- 1,000+ synthetic events processed
- 100% of runs traceable end-to-end (request to tool calls to output to human decision)
- 90%+ of seeded policy violations detected
- 80%+ automated test coverage on core services

## Our Domain: Supply Chain & Procurement

Policy rules and schema will cover things like:
- Spend limit thresholds and approval tiers
- Supplier eligibility / vetting criteria
- Contract term violations

(Schema, rule taxonomy, and seed sets are T5-specific — not shared with other teams.)

## Architecture

Reference shape (not mandated — we choose the real one):

Synthetic generator (seeded violations) leads into Ingestion + schema validation,
which leads into the Run store (runs, spans, violations, decisions),
which feeds three parallel components — Policy engine, Measurement harness, Audit log —
which all feed into the Review workflow (approve / reject / stop / rollback),
which feeds the Operator interface (trace view, search).

**Stack decisions:**
- Language/framework: **[TBD]**
- Database: **[TBD]**
- Frontend: **[TBD]**
- Rule format: **[TBD — YAML / JSON / DSL]**

## Checkpoints (freeze dates)

| Date | Checkpoint |
|---|---|
| Sep 15 | Event/trace schema frozen |
| Sep 29 | Dev + held-out evaluation seed sets separated (proposal gate) |
| Oct 13 | End-to-end trace completeness |
| Oct 20 | Declarative policy engine + violation explainability |
| Oct 27 | HITL state machine + rollback semantics (T5's deep-review Tuesday) |
| Nov 17 | One-command startup, 1,000-event search/filter perf |

## Ground Rules

- Private repo only — Prof. Seker added as collaborator, README + .gitignore in place before first commit
- Synthetic or public data only — never production/personal data
- No secrets, keys, or credentials in source control (including deleted branches)
- Dependency licenses checked and recorded
- AI tool use permitted with disclosure — see AI_DISCLOSURE_LOG.md

## Communication

- Email subject lines: CS4485-T5 — topic
- Technical questions go in the weekly report (Question 7), not email
- Weekly report due Friday 11:59 PM

## Status

Current status: Green
