---
type: article
description: "Canonical weekly revenue cadence, stage gates, founder ledger, and future dashboard contract."
status: canonical
supersedes: [ research/operating-state-and-revenue-sequencing.md ]
authored: 2026-07-26
author: Lalo, consolidated by Codex
tags: [ article, canonical, gtm, sales, operations, dashboard, internal ]
title: Founder-led growth operating system
sources:
  - research/operating-state-and-revenue-sequencing.md
  - external-sources/linear-operating-snapshot-2026-07-26.md
  - research/founder-interview-round-4-2026-07-26.md
---

## Summary

Agentic Engineering will run a founder-led, evidence-first revenue system before scaling lead volume or building a new command-center application. The system turns proof assets and account research into qualified conversations, proposals, paid work, and reusable delivery evidence. Automation may discover, verify, score, draft, and summarize; a human approves every external send, price, proposal, scheduling commitment, CRM stage change with commercial consequences, and customer-visible claim.

The current 30-day operating window is 2026-07-26 through 2026-08-25. Its two primary lanes are Agentic Engineering agency cash generation and a separate Curia paid-pilot motion, consistent with the [portfolio and platform strategy](./portfolio-and-platform-strategy.md).

## Offer architecture

### Agentic Engineering

1. Free Workflow Fit Check.
2. Paid Agent Systems Blueprint: standard public reference US$4,000; localized Mexico access may differ by eligibility.
3. Bounded pilot: US$8,000 / US$12,000 / US$15,000 reference tiers.
4. Operations retainer: US$2,500 / US$5,000 monthly reference tiers.

Pricing references come from current Sites and Linear evidence, not a blanket promise for every geography or scope [sources](../external-sources/sites-portfolio-snapshot-2026-07-26.md).

### Curia

Curia has its own narrow law-firm pilot and SaaS motion. It does not inherit the agency offer ladder. Curia pricing, contracting, governance, evidence, and fundraising remain separate; see [Curia GTM and pricing](./curia-gtm-pricing-playbook.md).

### Multiempaques exception

- Wait for sufficient operating data.
- Deliver the Blueprint free as a one-time early-client validation exception.
- Start the 7–10-day pricing window only when the data-completeness gate is met.
- Present scope and price after the Blueprint.
- Start paid implementation only after explicit acceptance.
- Record the exception so it does not silently reset the standard Blueprint price.

## Revenue workflow

```mermaid
flowchart LR
    P["Proof asset"] --> D["Discover account"]
    D --> V["Verify evidence"]
    V --> Q["Qualify workflow + sponsor"]
    Q --> R["Draft outreach or meeting prep"]
    R --> H["Human approval"]
    H --> C["Conversation"]
    C --> B["Blueprint / pilot proposal"]
    B --> W["Paid work"]
    W --> E["Reusable evidence + harness"]
    E --> P
```

### Qualification gates

An account becomes qualified only when the ledger contains:

- a recurring, costly workflow;
- a decision owner;
- a credible technical or operational sponsor;
- evidence that relevant data and systems can be accessed lawfully;
- a plausible outcome worth at least three times the proposed engagement;
- a defined next action and owner.

If a required field is unknown, store `unknown`; do not ask a model to infer it.

## Weekly cadence

| Day | Founder outcome | Agent support | Required record |
|---|---|---|---|
| Monday | Choose one ICP, one offer, and 15–50 named accounts | Discover, verify, dedupe, score | Account evidence envelopes |
| Tuesday | Approve top account briefs and outreach drafts | Draft personalized messages and Fit Check paths | Approval/rejection and edit distance |
| Wednesday | Conduct calls and capture workflow evidence | Meeting prep, transcript summary, objection tagging | Conversation, pain, sponsor, next action |
| Thursday | Build proposals and follow-up assets | Requirement traceability, option drafting, claims review | Proposal amount, decision gate, follow-up date |
| Friday | Review funnel, cash, delivery risk, and experiments | Aggregate metrics and exceptions | Weekly founder ledger and next-week decision |

No send or publish occurs solely because the calendar reached a cadence step.

## 30-day allocation

### Primary lane: Agentic Engineering agency

- Complete the Multiempaques sufficient-data gate and free Blueprint; start its 7–10-day pricing clock only when that gate is recorded.
- Validate one 50-account segment before considering a 500-account expansion.
- Optimize for qualified decision-owner conversations, priced proposals, and prepaid work, but do not present desired counts as forecasts until a live baseline exists.
- Use the Fit Check, Field Notes, and Proof Foundry only where their CTA, availability, and claims have been verified.
- MemSWE and Prism may support private conversations as owner-controlled proof artifacts; they are not acquisition entry points until a public, claims-reviewed CTA exists.

### Primary lane: Curia

- Re-verify KLGV pilot evidence, live privacy wording, and production gaps.
- Define one narrow pilot outcome and prepare research for a second design partner.
- Treat another paid design partner as a desired outcome, not current traction or a forecast.
- Do not contact or commit a new pilot until claims, product-readiness, privacy, and commercial gates are approved.

### Bounded validation gates

- PriceGenius: establish chain of title, one buyer, one measurable pricing workflow, a safe demo specification, and a credible paid signal before major build.
- Ultimate Harness: own one canonical evaluation corpus, strong baselines, provider-family-aware review, and a promotion decision before platform-superiority claims.
- Defade: re-verify the live revision, checkout, support, and analytics; select one segment and one offer; set numeric conversion thresholds only after a baseline exists.
- Muta: no additional build until ownership, product state, buyer, and customer evidence are reconciled and founders approve the next test.

## Funnel stages

| Stage | Entry rule | Exit evidence |
|---|---|---|
| Researched | Account and provenance exist | ICP fit scored |
| Qualified | Workflow, owner, sponsor, access, and value gate pass | Human approves contact |
| Contact-ready | Draft is evidence-grounded and approved | Message sent by authorized human/system |
| Conversation | Two-way response or meeting | Pain, decision process, and next action recorded |
| Solution fit | Bounded outcome and data/access assumptions agreed | Blueprint or pilot proposal approved |
| Proposal | Scope, price, expiry, and decision date delivered | Accepted, rejected, or explicit follow-up |
| Won | Payment or binding order received | Delivery handoff complete |
| Learned | Outcome and loss/win reasons captured | Evidence feeds offer and harness updates |

A list of leads is not pipeline until stage, owner, last touch, and next action are current.

## Founder operating ledger

The ledger is the contract for the future daily-driver dashboard.

| Object | Required fields |
|---|---|
| Account | stable ID, company, ICP evidence, owner, source, stage, last touch, next action |
| Evidence | atomic claim, source URL/path, observed date, snippet, confidence, allowed use |
| Contact | role, public/provided contact channel, consent or lawful-use basis, account link |
| Opportunity | offer, amount/currency, probability, decision date, blocker, owner |
| Touch | draft/approved/sent state, channel, timestamp, outcome, human approver |
| Workstream | Linear issue/project, owner, expected outcome, blocker, next milestone |
| Cash | invoiced, collected, due, expected delivery cost, currency |
| Agent run | mission, model/route, prompt version, cost, latency, result, acceptance, artifact |
| Decision | decision, owner, date, evidence, review date, superseded-by link |

### Source-of-truth rule

- CRM owns accounts, contacts, touches, and opportunities.
- Linear owns work and delivery status.
- The wiki owns claims, decisions, playbooks, and evidence policy.
- Finance ledger owns cash and runway.
- Agent run ledger owns model cost and output acceptance.
- Calendar and email are read surfaces; they do not replace CRM records.
- The dashboard reads these systems and should not silently become a second write authority.

Twenty is the current working mirror for confirmed contacts in the landing-page plan, pending the open CRM architecture decision in AE-370 [source](../external-sources/linear-operating-snapshot-2026-07-26.md). Older HubSpot work remains operationally superseded unless that decision authorizes a migration. Gmail remains unavailable until OAuth is repaired; Paperclip is excluded until remote health returns [source](../external-sources/chronicle-and-runtime-snapshot-2026-07-26.md).

## Daily-driver dashboard contract

The future Lalo/Lucy view should answer, in one screen:

1. What needs a founder decision today?
2. Which accounts need a next action?
3. Which opportunities changed stage, amount, or risk?
4. What agents completed, failed, or need review overnight?
5. Which delivery work is blocked?
6. What cash was collected, is due, or is at risk?
7. Which claims or customer evidence expire or conflict?
8. Which three outcomes matter today?

Build the UI only after the ledger can produce these answers without manual reconciliation.

## Metrics

### Leading

- accounts with verified evidence;
- qualified-account rate;
- draft acceptance and edit distance;
- founder minutes per accepted draft;
- conversations booked;
- proposals delivered;
- next-action hygiene;
- cost per accepted artifact.

### Lagging

- replies and meetings;
- proposal acceptance;
- prepaid revenue and collection time;
- gross contribution by engagement;
- pilot-to-retainer conversion;
- retention, expansion, and churn once recurring cohorts exist.

## Governance

- No invented personalization, customer metric, quote, or production claim.
- No autonomous send, publish, schedule, price change, contract acceptance, or customer-visible CRM write.
- No model handles untrusted browsing and external writing in one uninterrupted authority path.
- High-value artifacts receive fresh different-family review.
- Every exception is recorded with owner, reason, expiry, and review date.
- Stale data is labeled rather than silently treated as current.

## References

- [Operating state and revenue sequencing](../research/operating-state-and-revenue-sequencing.md)
- [Linear operating snapshot](../external-sources/linear-operating-snapshot-2026-07-26.md)
- [Founder interview — Round 4](../research/founder-interview-round-4-2026-07-26.md)
- [Delivery process](./delivery-process.md)
- [Ideal client profile](./ideal-client-profile.md)
