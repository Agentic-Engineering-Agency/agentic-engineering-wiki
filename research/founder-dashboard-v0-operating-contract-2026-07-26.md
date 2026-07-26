---
type: research-note
title: Founder dashboard v0 operating and data contract — 2026-07-26
description: Implementation-ready read-only specification for Lalo and Lucy, grounded in current ledgers, connector health, code surfaces, Sites patterns, and Linear sequencing.
status: provisional
sources:
  - external-sources/founder-dashboard-source-snapshot-2026-07-26.md
  - articles/founder-led-growth-operating-system.md
  - articles/portfolio-and-platform-strategy.md
  - articles/claims-registry.md
  - research/linear-reconciliation-result-2026-07-26.md
  - research/founder-interview-round-4-2026-07-26.md
created: 2026-07-26
author: Codex with founder-approved scope
tags: [research, provisional, dashboard, operations, founders, data-contract, revenue, agents]
---
# Founder dashboard v0 operating and data contract — 2026-07-26

## Question

What is the smallest trustworthy daily-driver dashboard for Lalo and Lucy that surfaces decisions, revenue, delivery, meetings, agent work, company health, and evidence without becoming another source of truth or crossing the approved no-send/no-deploy boundary?

## Sources cited

- [Founder dashboard source snapshot](../external-sources/founder-dashboard-source-snapshot-2026-07-26.md)
- [Founder-led growth operating system](../articles/founder-led-growth-operating-system.md)
- [Portfolio and platform strategy](../articles/portfolio-and-platform-strategy.md)
- [Claims registry](../articles/claims-registry.md)
- [Linear reconciliation result](./linear-reconciliation-result-2026-07-26.md)
- [Founder interview — Round 4](./founder-interview-round-4-2026-07-26.md)

## Decision

Founder dashboard v0 is a read-only morning operating view over explicit source contracts and normalized ledger projections. It is not a new CRM, finance system, issue tracker, agent scheduler, inbox, or approval authority.

The system must start useful with partial data. Linear, Sites, bounded Calendar, connector-scoped GitHub, explicitly instrumented PostHog projects, and Apollo aggregates are currently readable; Gmail, Paperclip, authoritative CRM opportunity state, finance actuals, and wider GitHub coverage are not [source](../external-sources/founder-dashboard-source-snapshot-2026-07-26.md). A blocked or unconfigured source therefore produces a visible degraded-state card, never an empty-success card or an invented zero.

The UI is a later implementation. The current deliverable is the source-of-truth map, normalized object contract, information hierarchy, role boundary, degraded-state behavior, KPI dictionary, fixtures, and acceptance tests required by AE-388 and LP-23 [source](./linear-reconciliation-result-2026-07-26.md).

## Product boundary

### v0 includes

- one Today view for founder decisions, top outcomes, overdue gates, meetings, revenue/delivery changes, and overnight agent exceptions;
- separate AE and Curia revenue/evidence lanes;
- read-only source-health, opportunity, workstream, delivery, artifact, claim, agent-run, and finance placeholders;
- direct links back to authoritative systems and wiki evidence;
- explicit observed-at, refreshed-at, time-window, denominator, currency, source state, and scope labels;
- a fixture/demo mode that proves partial-source behavior before any live deployment.

### v0 excludes

- sending email, messages, proposals, posts, or invitations;
- approving prices, claims, contracts, stages, or external content;
- mutating CRM, Linear, Calendar, GitHub, Sites, PostHog, Paperclip, or agent runtimes;
- merging, deploying, publishing, changing access, archiving, deleting, rotating credentials, or creating accounts;
- autonomous prioritization that replaces a named human owner;
- blending AE and Curia revenue, traction, customer, entity, raise, or IP claims;
- treating forecasts, deck numbers, historical lead batches, fixtures, or missing data as live business facts.

These exclusions preserve the current human-approval and entity-separation rules [sources](../articles/founder-led-growth-operating-system.md, ../articles/portfolio-and-platform-strategy.md).

## Information hierarchy

The dashboard opens in this order:

1. **Source health:** what is healthy, stale, scoped, blocked, not configured, or unknown.
2. **Founder decisions:** approvals or choices due today, overdue gates, owner, evidence, and consequence.
3. **Three outcomes today:** one owner and next action for each; no model-generated priority becomes authoritative without human selection.
4. **Revenue and delivery:** separate AE and Curia lanes, then bounded product validations.
5. **Meetings and inbox:** Calendar when live; Gmail remains a blocked tile until separately reauthenticated.
6. **Overnight agents:** completed, failed, awaiting review, spend/error signal, artifact, validation, and stop condition.
7. **Work and risk:** Linear blockers, overdue work, repository/deployment scope, and customer-delivery gates.
8. **Cash and raise readiness:** actuals only from a future reconciled finance ledger; assumptions stay visibly separate.
9. **Claims and evidence:** expiring, conflicting, prohibited, or approval-needed claims.

### Suggested shell

| Surface | Primary content | Existing pattern to reuse |
|---|---|---|
| Today | decisions, three outcomes, meetings, source health | Cifra daily home and progressive setup |
| Revenue | AE pipeline, Curia pipeline, next action, age, value, confidence | LP-23 funnel and founder ledger |
| Delivery | Multiempaques gate, Curia pilot evidence, client milestones | Multiempaques meeting cockpit and AE proof artifacts |
| Agents | missions, active/recent runs, acceptance, cost, failures | Ultimate Harness typed run/event/cost surfaces |
| Company | cash actuals, runway inputs, entity/raise readiness | AE weekly-review information architecture |
| Claims | contradictions, evidence, permitted audience, approver | Claims registry and Curia traceability cards |

Observed reusable UI patterns are documented in the point-in-time source snapshot [source](../external-sources/founder-dashboard-source-snapshot-2026-07-26.md). Reuse interaction and data-contract ideas, not product-specific storage or whole dashboards.

## System shape

| Layer | Responsibility | May write? |
|---|---|---|
| Source adapter | Perform bounded read, strip secrets/PII, emit source envelope | No |
| Source envelope | State provenance, timestamps, authority, scope, and degraded state | No external write |
| Normalizer | Map source-specific records to ledger projections | Local/ephemeral only |
| Daily read model | Calculate cards, queues, and KPI states from normalized records | Local/ephemeral only |
| Founder UI | Display, filter, link to source, and explain missing data | No |

A later implementation should use a new read-only business data layer and founder shell. Existing Ultimate Harness, Landing Page, PriceGenius, and weekly-review surfaces are evidence for adapters and components, not a mandate to extend any dirty or reserved repository [source](../external-sources/founder-dashboard-source-snapshot-2026-07-26.md).

## Source envelope contract

Every adapter result must emit:

| Field | Rule |
|---|---|
| source_id | Stable connector/system identifier |
| source_record_id | Stable upstream record ID when provided |
| entity_scope | AE, Curia, UH/platform, PriceGenius, Defade, Muta/incubation, or proof asset |
| authority | authoritative, working mirror, evidence-only, aggregate-only, or unverified |
| source_status | healthy, stale, scoped, blocked, not_configured, or unknown |
| observed_at | Timestamp represented by the upstream record |
| fetched_at | Timestamp of the successful or failed read |
| freshness_sla | Per-source expected age before stale |
| last_success_at | Last successful authoritative read, if known |
| error_code | Stable machine-readable code, never a secret-bearing stack trace |
| status_reason | Short founder-readable explanation |
| provenance_uri | Link/path back to the upstream record or evidence |
| allowed_operations | Read-only in v0 |
| redactions | Fields dropped before normalization |
| schema_version | Version of the adapter contract |

Mandatory redactions include connector tokens, credentials, cookies, secrets, private message bodies unless explicitly required later, direct personal contact details in aggregate founder views, and any cross-client confidential data. PostHog api_token fields and the plaintext credential-bearing root config file are specifically excluded [source](../external-sources/founder-dashboard-source-snapshot-2026-07-26.md).

## Degraded-state semantics

| State | Meaning | UI behavior |
|---|---|---|
| healthy | Successful read inside freshness SLA and within declared scope | Show value, window, source, fetched-at |
| stale | Prior successful value exists but is older than SLA | Show prior value with stale badge and age; never imply current |
| scoped | Read is healthy but connector coverage is narrower than the requested universe | Show value plus exact coverage boundary |
| blocked | Authentication, connectivity, permission, or upstream failure prevents read | Show reason and safe recovery owner; no number |
| not_configured | No approved connector or source contract exists | Show setup gap; no number |
| unknown | Evidence is insufficient to classify | Show unknown and needed evidence; no number |

A displayed zero is valid only when all of the following hold:

1. the authoritative or explicitly aggregate-only query succeeded;
2. its time window, entity scope, filters, and denominator are visible;
3. the adapter did not truncate or silently narrow coverage;
4. fetched-at is inside the freshness SLA;
5. the metric definition permits zero.

Apollo's observed last-seven-day zeroes satisfy an aggregate query boundary but do not establish a zero canonical CRM pipeline [source](../external-sources/founder-dashboard-source-snapshot-2026-07-26.md).

## Normalized ledger projections

### Account

stable ID; entity scope; company; public ICP evidence; source; owner; stage; last touch; next action; next-action date; age; consent/lawful-use state; evidence confidence.

### Contact

stable ID; account link; role; public/provided channel; consent or lawful-use basis; last verified date. Direct personal data is hidden from aggregate founder cards by default.

### Opportunity

stable ID; entity/raise lane; company; offer; stage; amount; currency; confidence; owner; next action; next-action date; decision date; blocker; source; evidence; last changed date.

### Touch

account/opportunity; channel; draft/approved/sent state; timestamp; outcome; human approver; source. v0 reads this record but never advances it.

### Workstream

Linear issue/project; entity scope; owner; expected outcome; priority; status; blocker; next milestone; due date; updated-at.

### Delivery gate

client/product; gate name; state; prerequisite; owner; observed date; target window; evidence; next action. Multiempaques pricing timing is computed only from a recorded sufficient-data gate date, never first-file receipt or an artificial due date [sources](../articles/founder-led-growth-operating-system.md, ./linear-reconciliation-result-2026-07-26.md).

### Evidence and claim

atomic claim; claim state; source path; observed date; confidence; allowed audience/use; approver; review date; conflict/supersession link. Customer, pricing, entity, traction, and model-superiority claims remain governed by the claims registry [source](../articles/claims-registry.md).

### Cash actual

entity; account; amount; currency; kind; invoice date; due date; settled date; payment status; source; observed-at. Forecasts and cap-table assumptions use separate record types and never populate actual cards.

### Agent run

run ID; entity/project scope; objective; runtime; exact provider; exact model/version; prompt/harness version; status; started/ended/last-event; artifact URIs; reviewer; reviewer provider family; acceptance; tokens; cost/currency; latency; error; retry; stop condition; source health.

### Decision

decision; entity scope; owner; due/review date; options; evidence; consequence; approval state; source; superseded-by link.

### Artifact/deployment

artifact ID; project; source commit/version; saved version; deployment state; live URL; access mode; updated-at; claims review state. Latest saved version and live production state remain distinct until a deployment link is verified [source](../external-sources/founder-dashboard-source-snapshot-2026-07-26.md).

## Entity and portfolio partition

Every revenue, customer, cash, claim, raise, and pipeline record carries one entity scope. The default views are:

- **Agentic Engineering:** agency cash engine plus platform/IP validation owned or intended for AE subject to chain of title;
- **Curia:** separate product, customer evidence, Mexican SAPI target, and separate raise;
- **Portfolio validation:** Defade, PriceGenius, Muta, Agentforge, SpecSafe, or other options, each with an explicit owner and evidence gate;
- **Proof assets:** Prism Arena and MemSWE as evidence, not revenue unless a separate transaction record exists.

A portfolio rollup may count workstreams or risks, but it may not add Curia customer evidence, revenue, or fundraising claims to AE. This separation is a founder-approved operating rule, while formation and assignment remain target states until verified [sources](../articles/portfolio-and-platform-strategy.md, ./founder-interview-round-4-2026-07-26.md).

## KPI dictionary

Every KPI card must show formula, numerator, denominator, entity, currency where relevant, window, exclusions, source state, and calculated-at.

### Agentic Engineering

| KPI | Definition |
|---|---|
| Verified accounts | Accounts passing the current evidence contract in the selected AE segment |
| Qualified-account rate | Qualified accounts divided by reviewed accounts in the same bounded cohort |
| Next-action hygiene | Active accounts/opportunities with current owner, next action, and due date divided by active records |
| Conversations | Two-way replies or held meetings recorded in the authoritative pipeline for the period |
| Proposals delivered | Proposals with scope, price, expiry/decision date, and human-approved delivery evidence |
| Proposal acceptance | Accepted proposals divided by proposals reaching an explicit accepted/rejected decision |
| Collected cash | Settled cash actuals for AE in original currencies; no silent currency conversion |
| Multiempaques gate | data pending, sufficient-data recorded, Blueprint in progress/complete, price due window, accepted/rejected |

### Curia

| KPI | Definition |
|---|---|
| Paid design partners | Verified current paid Curia design partners, not AE customers |
| Active users | Defined product users inside an explicit window and product project |
| Repeated workflows | Same qualified Curia workflow completed on multiple dates inside the window |
| Verified outputs | Outputs passing the agreed legal/source review gate |
| Issues resolved | Pilot issues closed with evidence and denominator |
| Renewal/expansion signal | Explicit, dated customer signal; not model-inferred sentiment |
| Second-firm readiness | Qualified firms and readiness gates, separate from contacted or contracted firms |

### Operations and agents

| KPI | Definition |
|---|---|
| Source health | Healthy/scoped sources divided by expected sources, with blocked sources listed separately |
| Accepted artifact rate | Accepted reviewed outputs divided by outputs receiving a disposition |
| Cost per accepted artifact | Tracked model/tool cost divided by accepted artifacts in the same workflow/version window |
| Run failure rate | Failed terminal runs divided by terminal runs, excluding still-active runs |
| Overdue founder decisions | Open decisions past due with a named human owner |

No target count becomes a forecast or traction claim without a measured baseline and named evidence [source](../articles/founder-led-growth-operating-system.md).

## Founder role and permission model

v0 has two internal viewer personas: Lalo and Lucy. Both use the same underlying data contracts; the UI may default to My items versus All items based on ownership. No v0 control performs an external or authoritative write.

Each card exposes:

- source and freshness;
- named human owner;
- evidence/detail link;
- why the item appears;
- missing/blocked data explanation;
- optional local view preference only.

Any future approval, send, CRM-stage change, agent stop, issue update, price decision, or publication requires a separately designed write path, explicit authority, audit record, and user acceptance. It is not hidden behind a disabled-looking v0 control.

## Decision queue contract

A queue item is eligible only when it has:

- a named human owner;
- entity scope;
- requested decision and consequence;
- due or review date;
- evidence/provenance link;
- explicit approval state;
- originating issue/workstream;
- no automatic execution side effect.

The first queue should include source/credential remediation decisions, Multiempaques gate readiness, AE/Curia claim conflicts, CRM authority, finance-ledger authority, and review-required agent artifacts. It should not invent urgency from an unverified date.

## Implementation sequence

### Phase 0 — accepted contract and fixtures

1. Approve this object/source contract and the canonical ledger storage decision.
2. Create fixtures for healthy, stale, scoped, blocked, not-configured, and unknown sources.
3. Create separate AE and Curia fixture records plus a prohibited cross-entity aggregation case.
4. Define metric formulas and freshness SLAs.
5. Define secret/PII redaction tests.

### Phase 1 — read-only useful slice

1. Linear work/decision adapter.
2. Sites artifact/deployment-evidence adapter.
3. bounded Calendar adapter.
4. connector-scoped GitHub adapter.
5. PostHog aggregate adapter with strict allowlist and token stripping.
6. Apollo aggregate activity/credit adapter without enrichment.
7. Today shell with degraded-state cards and source links.

Phase 1 excludes Gmail, Paperclip, CRM opportunity sync, finance actuals, and write actions until their separate blockers and authority contracts are resolved [source](../external-sources/founder-dashboard-source-snapshot-2026-07-26.md).

### Phase 2 — authoritative business ledgers

1. decide canonical CRM and read direction under AE-370;
2. establish versioned founder opportunity ledger;
3. establish separate AE and Curia finance actuals ledgers;
4. reconcile duplicate AE cap-table workbooks;
5. reauthenticate Gmail only in a separately approved access-change step;
6. restore and verify Paperclip/Tailscale before live agent-state integration.

### Phase 3 — separately approved actions

Only after v0 proves reliability: design explicit, narrowly authorized write actions with previews, confirmation boundaries, idempotency, audit logs, rollback where possible, and per-system permissions. This phase is outside the current authorization.

## Deterministic acceptance tests

- A Gmail auth failure renders blocked plus reason and no unread count.
- A stale source renders its last value, stale age, and last-success timestamp.
- A scoped GitHub connector never labels its two visible repositories as the whole organization.
- A zero displays only after a successful query with visible window, scope, and denominator.
- A PostHog payload cannot expose, log, cache, or forward api_token.
- The root credential-bearing config file cannot be loaded as a dashboard source.
- AE and Curia opportunity, cash, customer, claim, and raise records cannot cross default partitions.
- Two conflicting cap-table files produce a reconciliation blocker, not a combined value.
- Multiempaques price timing stays unset until a sufficient-data gate timestamp exists.
- Latest saved Sites version does not automatically equal live deployment revision.
- An agent card without exact provider/model/version or artifact evidence is marked incomplete.
- A model review does not equal human approval.
- No UI route or adapter can send, approve, mutate, merge, deploy, publish, change access, archive, or delete.
- Fixture mode is visibly labeled and cannot be mistaken for live operations.

## Linear sequencing

AE-388 remains the specialized spec deliverable related to LP-23; it should not replace the founder-led growth parent. The logical sequence is:

1. LP-23 ledger/stage/approval contract;
2. AE-369 selected-segment evidence;
3. UH-142 canonical run/evaluation envelope, then LP-25 sales slice;
4. AE-388 source contract, wireframe, KPI/freshness definitions, and degraded-state fixtures;
5. a separate implementation issue only after spec acceptance;
6. AE-370 only when CRM sync or migration enters scope.

AE-387 runs event-driven in parallel and remains externally data-gated. Claim/entity truth under AE-254, AE-389, and AE-390 precedes investor-facing aggregation [sources](./linear-reconciliation-result-2026-07-26.md, ../external-sources/founder-dashboard-source-snapshot-2026-07-26.md).

## Open questions

- Which versioned system stores the founder opportunity ledger before the CRM decision?
- Which finance system is authoritative for separate AE and Curia cash actuals?
- Which decisions and financial fields should default to Lucy versus Lalo, if any?
- What freshness SLA applies to each connector?
- Who owns Gmail reauthentication and Paperclip/Tailscale restoration?
- Should the first implementation live in a new repository or a clean worktree after current sessions reconcile?
- What exact data fields constitute the Multiempaques sufficient-data gate?

## Recommendation

Accept this as the AE-388 v0 contract, keep the current batch documentation-and-Linear-only, and create a distinct implementation issue after the ledger storage and fixture contract are approved. The first implementation slice should prove truthful partial data and AE/Curia partitioning before visual polish, write actions, or production deployment.