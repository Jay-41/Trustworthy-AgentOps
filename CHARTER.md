# T5 Team Charter — Trustworthy AgentOps: Supply Chain & Procurement

## Problem Statement

In supply chain and procurement, AI agents can be given real authority: recommending suppliers, approving purchase orders, or flagging contract terms without a human always in the loop. When an agent approves a purchase over a spend threshold, selects an ineligible supplier, or misses a contract-term violation, there's often no record of what triggered the action, why it was allowed, or who could have stopped it. Our system exists to make every procurement-agent decision observable, explainable, attributable to a human decision-maker, and reversible.

## Scope

What T5 will build:
- Event ingestion for procurement-agent runs (purchase requests, supplier selection, contract review actions)
- A policy engine enforcing spend-limit thresholds, supplier eligibility rules, and contract-term checks
- A trace view showing the full path of a procurement decision — request, agent/model calls, policy checks, outcome
- A review workflow supporting approve / reject / stop / simulated rollback on flagged procurement actions
- An append-only audit trail of every automated and human decision
- A synthetic data generator producing seeded procurement events and policy violations, with separate development and evaluation seed sets

## Non-Scope

What T5 will explicitly not build:
- Integration with real supplier, vendor, or ERP systems — synthetic/public data only
- Live agent framework integration — stretch goal only, not part of the core
- Production or real company procurement data of any kind
- Enforcement mechanisms outside the simulated environment (no real purchase orders are ever executed)

## Definition of Done

The system is done when:
- [ ] 1,000+ synthetic procurement events processed in a repeatable test run
- [ ] 100% of runs traceable end-to-end (request → agent/tool calls → outcome → human decision)
- [ ] 90%+ of seeded policy violations (spend-limit, supplier-eligibility, contract-term) detected
- [ ] 80%+ automated test coverage on core services
- [ ] One-command startup verified on a clean machine
- [ ] Every violation record shows the triggering rule, threshold, and evidence
- [ ] HITL state machine rejects invalid approve/reject/stop/rollback transitions

## Decision-Making Process

- **Technical decisions:** proposed by the member(s) working on that component, discussed at the team's weekly meeting, decided by majority if not unanimous.
- **Scope changes:** any member can propose one; must be discussed as a team and logged in that week's weekly report ("Scope change request" field) before being treated as approved.
- **Unresolved disagreements:** raised as the team's "one decision" (Question 7) in the weekly report for the advisor's input at the next Tuesday slot.
- **Stack/architecture choices:** decided as a team by the Sep 22 architecture review checkpoint; recorded with a written reason.

## Roles & Rotation

- Team leader, scribe, and time-keeper rotate weekly so each member experiences every role roughly twice per semester.
- POC: rotates weekly by default. The team may vote to keep the same POC for a longer stretch if every member, including the POC, agrees — to be revisited and recorded in a weekly report if changed.

## Team Members

| Name | UTD Email |
|---|---|
| Jay Trivedi | jht230000@utdallas.edu |
| Zakarias Zewdu | zxz210018@utdallas.edu |
| Neha Senthil-Kumar | nxs220105@utdallas.edu |
| Hafa Kazi | nsk210004@utdallas.edu |
| Zach Johnson | zmj230000@utdallas.edu |
| Jared Lillie | jjl220004@utdallas.edu |

## Agreement

All members agree to the above as of 9/11/2026:
Jay Trivedi, Zakarias Zewdu, Neha Senthil-Kumar, Hafa Kazi, Zach Johnson, Jared Lillie
