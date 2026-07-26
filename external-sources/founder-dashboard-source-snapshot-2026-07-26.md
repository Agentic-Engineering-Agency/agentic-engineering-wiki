---
type: source
title: Founder dashboard source snapshot — 2026-07-26
description: Point-in-time, read-only evidence capture for connector health, Sites, Linear, existing dashboard code, local business data, and agent-runtime constraints.
source_url: local://founder-dashboard-audit/2026-07-26
date_fetched: 2026-07-26
preservation: tool-observation
tags: [source, immutable, layer-ingest, internal, dashboard, operations, connectors]
---
# Founder dashboard source snapshot — 2026-07-26

## Source

Point-in-time read-only audit performed on 2026-07-26 across connected apps, live Linear issues, six accessible Sites projects, local non-Markdown code and machine-readable files, and current agent/runtime processes. No email, prospect message, CRM write, merge, deployment, publication, access change, archive, deletion, credential use, or Apollo credit-consuming enrichment occurred.

Secret values and personal contact data are intentionally omitted. The root workspace config file was observed to contain plaintext provider credentials; no value was read into this document, and the file must never become a dashboard source.

## Connector observations

| Source | Observed state | Evidence boundary | Dashboard-safe use |
|---|---|---|---|
| Linear | Confirmed | AE team and current issues readable on 2026-07-26 | Work, owner, priority, dates, relations, blockers, updated-at |
| Sites | Confirmed | Six accessible active projects; metadata, saved versions, commits, live URLs | Artifact status, latest saved version, update time, access mode |
| Google Calendar | Confirmed | Primary calendar bounded search returned a live event | Today and seven-day schedule; redact attendee/contact detail |
| GitHub | Confirmed, scoped | Connector exposes only .github-private and Defade in Agentic-Engineering-Agency | Repository/commit/PR/check facts only for connector-visible repositories |
| PostHog | Confirmed, mixed | Default, ShesMine, Curia-AI, Prospecting-Agent, and PriceGenius show ingestion; Agentic Engineering shows no ingested event | Aggregate metrics only after per-project definitions; drop connector api_token fields entirely |
| Apollo | Confirmed, aggregate-only | 295 lead credits remained; last-seven-day emails sent, meetings held, opportunities, and pipeline amount each returned zero | Aggregate activity and credit budget; not CRM truth; no enrichment without a separately approved credit gate |
| Gmail | Blocked | UNAUTHORIZED; oauth_token_invalid_grant; reauthentication required | Show blocked state only; do not render inbox metrics as zero |
| Twenty CRM | Working mirror, read side unverified | Current Landing Page integration upserts inbound people; no pipeline/stage read adapter found | Do not present as authoritative pipeline until AE-370 and a read contract are resolved |
| HubSpot / Salesforce | Not configured or unverified | No callable connector found | Show not-configured; never infer zero pipeline |
| Paperclip | Blocked | Remote health failed; SSH timed out; Tailscale reports expired peer node key | Show blocked connectivity; no live agent/mission/cost claims |
| Herdr | Partially observed | Server/processes visible, but this shell did not expose HERDR_ENV=1 control authority | Read process presence only; no control or mission scheduling from this shell |

PostHog connector responses may include an api_token property. Any adapter must remove that property before logging, caching, rendering, or forwarding data.

## Sites inventory

The connector exposed exactly six active owner-only custom projects. None had a preview URL, custom domain, or runtime environment variable. A latest saved version is observable, but the connector did not expose an absolute latest-saved-to-live deployment link; do not claim those are identical without deployment evidence.

| Project | Project ID | Latest saved evidence | Live URL |
|---|---|---|---|
| Cifra | appgprj_6a65614de2848191bd4cfbcb94c6b195 | v2; ecf9302211b9ae41c42d577a3a14624c93ecf440; updated 2026-07-26 | https://cifra-finance-command-center.agenticengineering.chatgpt.site |
| Multiempaques · Prep 30 | appgprj_6a6287818d2c8191b1216d349d848225 | v1; 6b7b45d666d1a6f8490e3ebe7ee7aceec580a4e3; updated 2026-07-23 | https://multiempaques-prep-30.agenticengineering.chatgpt.site |
| Curia — Investor Deck | appgprj_6a5683dbf5108191bc40a8e9eb5791f9 | v1; 013fa21572748880086f535c93ba7cc6d8c6587e; updated 2026-07-14 | https://curia-investor-deck.agenticengineering.chatgpt.site |
| Agentic Engineering — Investor Overview | appgprj_6a541ec349cc8191b7726f7e29d6c78f | v4; 338cdd0a9df56fc4371d07304bb7fe4041568888; updated 2026-07-14 | https://agentic-engineering-investor-overview.agenticengineering.chatgpt.site |
| Agentic Engineering — Client Sales | appgprj_6a541ebbad34819190dd7db354467c31 | v2; 860596c7823a89dd7ded8b0d13b81158ef5e2639; updated 2026-07-13 | https://agentic-engineering-client-deck.agenticengineering.chatgpt.site |
| MemSWE · Resultados PAP 2026 | appgprj_6a50250533dc819188d073395072cf89 | v9; aeb6e8c6a2180173d42693f2be288d01483acad6; updated 2026-07-17 | https://memswe-pap-2026.agenticengineering.chatgpt.site |

Reusable observed interaction patterns:

- Cifra: Today, Accounts & debts, Activity, and Plan navigation; capture inbox; progressive setup; review-before-save; explicit device-local state.
- Multiempaques · Prep 30: Audio, Ruta, Checklist, timer, and a focused meeting cockpit.
- Agentic Engineering investor overview: Signal → Route → Build → Prove stage taxonomy with tangible artifacts.
- Agentic Engineering client sales: proof screenshot, delivery dossier, linked artifacts, and human-reviewed status.
- Curia investor deck: evidence traceability, status chips, and case cards.
- MemSWE: KPI cards with evidence date, denominator, scope, report, and presentation routes.

## Existing implementation surfaces

| Surface | Exact path | Reusable evidence | Limitation |
|---|---|---|---|
| AE 5-week dashboard | /Users/eduardojaviergarcialopez/AgenticEngineering/Agentic-Engineering-GTM/ops/5-week-plan/ae-5wk-dashboard.html | Plan, risk, owner, cash/runway, Linear-query information architecture | Stale May prototype; hardcoded MCP tool ID, labels, owners, dates, and finance values |
| Weekly operating review | /Users/eduardojaviergarcialopez/AgenticEngineering/Agentic-Engineering-GTM/ops/weekly-review/workspace/iteration-2/benchmark.json | Cash/runway, KPIs, GTM tracks, risks, next actions, cross-system checks | Evaluation evidence is narrow and not an authoritative business ledger |
| Twenty inbound adapter | /Users/eduardojaviergarcialopez/AgenticEngineering/landing-page/lib/twenty-crm.ts | Typed failures, timeout, PII-safe logging, person upsert | Write-only inbound path; no account/opportunity/stage read model |
| Newsletter data model | /Users/eduardojaviergarcialopez/AgenticEngineering/landing-page/migrations/newsletter/0001_newsletter.sql | Consent, subscription, provider events, campaign draft → approved → sent states | Marketing lifecycle, not company pipeline |
| UH run surface | /Users/eduardojaviergarcialopez/AgenticEngineering/ultimate-harness/apps/hermes-plugin/dashboard/src/OverviewTab.tsx | Adapter, mission, active/recent run, polling, verification, cost patterns | One project root; no company, CRM, finance, inbox, or calendar aggregation |
| UH API bridge | /Users/eduardojaviergarcialopez/AgenticEngineering/ultimate-harness/apps/hermes-plugin/dashboard/plugin_api.py | SSE, run state, comparisons, verification, retention, safe ID validation | Existing repo is dirty; use as future read-adapter evidence, not a mutation target |
| PriceGenius dashboard | /Users/eduardojaviergarcialopez/AgenticEngineering/pricegenius/client/src/pages/Dashboard.tsx | KPI cards, alerts, recommendations, loading and empty states | Product-specific domain, not company operating truth |
| PriceGenius schema | /Users/eduardojaviergarcialopez/AgenticEngineering/pricegenius/convex/schema.ts | Automation, email, revenue analytics, organization, agent-run, insight record patterns | Product schema must not become cross-company authority without a new contract |

## Local machine-readable business data

| Source | Observed use | Readiness |
|---|---|---|
| Agentic-Engineering-GTM/investor-data-room/AE_CapTable.xlsx and Agentic-Engineering-GTM/data-room/AE_CapTable.xlsx | Two same-day capitalization workbooks | Conflicting potential authorities; reconcile before aggregates |
| Agentic-Engineering-GTM/data-room/AE_3yr_Projection.xlsx | Three-year planning model from 2026-05-07 | Forecast assumptions only; not cash or actuals |
| Agentic-Engineering-GTM/directory-publishing/AE_DIRECTORY_SUBMISSION_TRACKER.csv | Directory/channel tracking | Distribution coverage only; not lead or revenue truth |
| Agentic-Engineering-GTM/deployments/sites/*/SOURCE.json and built manifest.json files | Artifact provenance | Deployment/collateral freshness only |
| prism-arena/data/prism-arena.sqlite | Current benchmark/run evidence | Technical proof and run metrics; not commercial KPIs |
| pricegenius/.gsd/gsd.db | Local project-state database | PriceGenius task progress only |
| products_import.csv and sample CSV files | Fixtures and import samples | Exclude from business metrics |

No authoritative local source was found for current accounts, opportunities, stages, owners, next actions, proposals, booked revenue, collected cash, invoices, receivables, burn, runway, product usage, acquisition source, retention, or per-client economics.

## Linear observations

- LP-23 is In Progress, High, due 2026-08-25, and remains the canonical founder-led growth operating-system issue.
- AE-388 is Todo, Medium, assigned to Lalo, due 2026-08-12. It is a specialized dashboard-spec deliverable, not a duplicate of LP-23.
- AE-370 is Backlog and blocks only CRM implementation or migration, not ledger-first specification.
- AE-369 is Todo, High, due 2026-08-07; its current evidence favors an industrial manufacturer/distributor segment and retains accounting as comparison evidence.
- AE-387 is In Progress and blocked on external Multiempaques data. Its pricing clock has not started.
- UH-142 owns the canonical model/run corpus; LP-25 contributes the sales slice.
- AE-254 governs AE/Curia entity, raise, and chain-of-title separation.
- No dedicated current issue was found for ledger storage/version, finance actuals, Gmail reauthentication, Paperclip/Tailscale restoration, or post-spec dashboard implementation.

## Runtime and repository constraints

- Claude Code 2.1.220 and OMP 17.1.3 are installed. Three Claude interactive sessions plus a long-running OMP/Herdr Prism session were observed.
- Prism Arena, Landing Page, and Agentic-Engineering-GTM should be treated as reserved by current work. Landing Page and Ultimate Harness have uncommitted changes; no mutation is authorized here.
- OMP historical Prism statistics showed high tracked spend and a high error rate; that is a reason to require per-run acceptance and stop conditions, not a claim about every OMP workflow.
- Paperclip remote state cannot be presented as live until Tailscale, SSH, and API health all pass.

## Snapshot conclusion

A read-only v0 can truthfully aggregate Linear, Sites, bounded Calendar, connector-scoped GitHub, explicitly instrumented PostHog projects, and Apollo aggregates. It must label Gmail, Paperclip, CRM pipeline, finance actuals, and any broader GitHub or agent-runtime coverage as blocked, not configured, scoped, or unknown. No missing source may render as zero.