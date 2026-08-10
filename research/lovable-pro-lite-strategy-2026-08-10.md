---
type: research-note
description: >-
  Provisional strategy and operating guardrails for a 30-day experiment using the observed
  Lovable Lite account.
status: provisional
sources:
  - https://lovable.dev/pricing
  - https://lovable.dev/linkedin-premium-offer
  - https://lovable.dev/blog/simplifying-billing
  - https://docs.lovable.dev/features/cloud
  - https://docs.lovable.dev/integrations/github
  - https://docs.lovable.dev/features/plan-mode
  - https://docs.lovable.dev/features/publish
  - https://docs.lovable.dev/features/security
  - https://docs.lovable.dev/features/business/data-opt-out
  - https://docs.lovable.dev/integrations/lovable-mcp-server
  - https://docs.lovable.dev/features/workspace-admin-settings
  - articles/claims-registry.md
  - articles/founder-led-growth-operating-system.md
  - research/operating-state-and-revenue-sequencing.md
created: 2026-08-10
author: Codex
tags: [ research, provisional, lovable, gtm, agentic-engineering, revenue-workcell ]
title: Observed Lovable Lite account strategy for Agentic Engineering
---

## Question

What advantage does the observed Lovable Lite account provide alongside Codex, Claude Code, Kimi
Code, Qwen, OMP, onorca.dev, and other harnesses, and what bounded Agentic Engineering use should
receive its credits?

## Evidence state and sources

This note distinguishes three kinds of evidence:

- **Observed account snapshot:** a BrowserOS neo inspection of Lovable
  `Settings → Plans & credit usage` on 2026-08-10 confirmed the live account label `Lovable Lite`,
  US$5/month, 105 stored credits, 5 daily build credits, and a renewal day displayed as 8 August
  before the experiment began. After the first complete Revenue Workcell generation and its
  automated repair pass, the same surface showed 99.6 stored credits, zero daily credits, and
  10.4 credits used by this project. It states that the 99.6 stored credits expire on 8 August
  2027. The referenced Codex task separately recorded 4 AI credits and 20 Cloud credits; those
  two balances remain unverified until the separate Cloud and AI balance surface is inspected.
- **Current first-party documentation:** Lovable's public [pricing](https://lovable.dev/pricing)
  uses `Pro`, not `Lite`; an official [Pro Lite promotion](https://lovable.dev/linkedin-premium-offer)
  describes Pro features under a promotional offer; and Lovable has documented a
  [billing migration](https://lovable.dev/blog/simplifying-billing). These sources make the account
  label ambiguous rather than proving that the observed account has every public Pro entitlement.
- **Internal operating authority:** the [claims registry](../articles/claims-registry.md),
  [founder-led growth operating system](../articles/founder-led-growth-operating-system.md), and
  [operating-state and revenue sequencing note](./operating-state-and-revenue-sequencing.md) govern
  claims, human approval, and the near-term revenue objective.

The account name, price, pre-build and post-build credit balances, daily-credit balance, project
usage, displayed renewal day, and stated expiry above are **observed**. The complete entitlement
contract, renewal year, and Cloud/AI balances remain **unverified**. Lovable's
[workspace settings documentation](https://docs.lovable.dev/features/workspace-admin-settings)
separates plan/build-credit information from deployed-app Cloud and AI usage, so both surfaces must
be checked before changing the operating budget. No retrievable Perplexity artifact was available
in the referenced task or workspace, so no claim in this note is attributed to Perplexity. A
later report should be reconciled claim by claim against these sources.

## Findings

### Lovable's advantage is productization, not another coding intelligence layer

The useful complement to the existing coding agents and orchestration harnesses is Lovable's
short path from a decision-complete brief to a polished, hosted, customer-usable web experience.
Agentic Engineering should spend Lovable credits on the conversion and evidence surface that a
prospect can use, not on duplicating research, planning, coding-agent routing, or workflow
orchestration already handled elsewhere.

The bounded use is one bilingual **Agentic Engineering Revenue Workcell** with two role-based
experiences:

1. A **Founder Cockpit** for reviewed account evidence, source URLs, checked dates, evidence
   states, a deterministic Workflow Fit Check, Opportunity Map drafts, Blueprint proposal drafts,
   and named human approval gates.
2. An authenticated **Prospect Result Room** for a bilingual diagnostic, workflow and friction
   map, one to three ranked opportunities, baseline evidence, KPIs, assumptions, risks,
   exclusions, and a human-reviewed Agent Systems Blueprint proposal. US$4,000 is reference
   pricing only, subject to scope, eligibility, claims review, and approval by the human commercial
   owner before it becomes prospect-visible.

This is a readiness and proposal workflow, not an automated diagnosis or autonomous sales system.
Any KPI value that lacks dated evidence must be labeled as a hypothesis. The application must not
imply ROI, savings, customer approval, or commercial acceptance without evidence permitted by the
[claims registry](../articles/claims-registry.md).

### The Revenue Workcell must remain a bounded evidence layer

The approved implementation plan specifies the following boundaries. They do not supersede the
canonical wiki: Notion can host decision workflow, while Wiki/OpenKnowledge owns the durable
decision, claim, and provenance record.

| Concern | Authority | Revenue Workcell responsibility |
|---|---|---|
| Decision workflow | Notion | Present decision-workflow references; do not become the decision log |
| Execution state | Linear | Display or link approved state; do not become the task tracker |
| Code and release evidence | GitHub | Synchronize application code and retain review/rollback evidence |
| Decisions, claims, provenance | Wiki/OpenKnowledge | Carry sources, dates, states, and use limits |
| Confirmed-contact CRM | Twenty | No CRM write in version 1 |
| Shared client collaboration | Sila | Begin only after qualification |
| External connections | Composio | Server-side, narrowly scoped, and read-only in version 1 |

Lovable Cloud may hold authentication, tenant membership, presentation/session state, derived
drafts, and server-side functions under its
[Cloud model](https://docs.lovable.dev/features/cloud). It must not become an operating ledger or
hold authoritative account, contact, touch, opportunity stage/price, decision, or claim records.
It also must not hold unrestricted workspace payloads, client source code, credentials, sensitive
financial data, or direct-contact research.

### Portability and access controls are release gates

The Lovable project now exists and is synchronized bidirectionally with the dedicated private
repository `Agentic-Engineering-Agency/agentic-engineering-revenue-workcell`. Do not repurpose the existing `ae-workcell`
execution-control project. Because Lovable's documented workflow does not import an existing
repository, the project should originate in Lovable and connect to GitHub immediately for
two-way synchronization, local review, rollback, and portability. See
[GitHub synchronization](https://docs.lovable.dev/integrations/github).

The Cloudflare site remains the public acquisition front door and sends qualified visitors to the
authenticated result room. Link-public platform publication is not authorization to expose
records: every prospect record requires authentication, tenant isolation, and tested row-level
security. Lovable's [publishing controls](https://docs.lovable.dev/features/publish) and
[security guidance](https://docs.lovable.dev/features/security) inform the configuration but do
not replace an independent security review.

Use sanitized demonstration data until Lovable Support provides dated confirmation that the
documented Free/Pro
[training-data opt-out request](https://docs.lovable.dev/features/business/data-opt-out) has been
applied to this account. Do not connect the governed multi-agent environment to production Lovable
projects through the research-preview
[Lovable MCP server](https://docs.lovable.dev/integrations/lovable-mcp-server): its account-wide
access and mutation/credit capabilities exceed the version 1 boundary. If evaluated, use a
separate empty workspace.

On 2026-08-10 the project also enabled Lovable Cloud and generated an OAuth-protected MCP surface
with four read-only tools over sanitized fixtures. Neither event authorizes publication or real
data. Local review disabled invocation telemetry, bounded OAuth/tool inputs, added anti-framing
headers, and recorded client/tenant authorization, RLS, edge limits, redirect registration, and
canonical-host verification as publish gates. The project remains unpublished.

## Credit operating plan

Prepare research, schemas, bilingual copy, prompts, and acceptance criteria outside Lovable.
[Plan mode](https://docs.lovable.dev/features/plan-mode) consumes credits per message, so use it
only for project-local implementation decisions.

| Envelope | Credits | Intended outcome |
|---|---:|---|
| Shared shell, design system, authentication, roles | 15 | One secure bilingual application shell |
| Founder Cockpit | 25 | Evidence review and human approval workflow |
| Diagnostic and Prospect Result Room | 25 | Tenant-isolated diagnostic and result experience |
| Opportunity Map and proposal workflow | 15 | Ranked opportunities and reviewed proposal draft |
| Read-only integrations and freshness/error states | 10 | Narrow adapters with visible provenance and failure states |
| Bilingual, responsive, accessibility, and security QA | 10 | Release gates on mobile and desktop |
| Contingency | 5 | Bounded repair reserve |

The initial build consumed all five daily credits plus 5.4 stored credits. Treat the remaining
99.6 stored credits as the live ceiling and require a scoped acceptance criterion before every
follow-up build. Reserve deployed-app AI for an account-specific Opportunity Map or proposal
narrative; scoring stays deterministic and has a non-AI template fallback. One tenant-isolated
project serves all prospects. Record build, Run/Cloud, and AI consumption per completed diagnostic
and qualified conversation.

## Acceptance gates

### Technical gate before real data

- Founder and prospect roles cannot access one another's restricted data.
- One prospect cannot read another prospect's records.
- No outreach, CRM write, proposal approval, or claim publication occurs without a named human
  action.
- No proposal becomes prospect-visible without approval from the human commercial owner and a
  claims review; displayed pricing remains a reference until then.
- Every derived recommendation retains its source, checked date, and evidence state.
- English and Spanish flows work on mobile and desktop.
- GitHub synchronization and rollback are proven.
- Authentication, row-level security, independent security review, and browser-tested critical
  flows pass.
- Only sanitized demonstration data is present before all gates pass.

### Commercial gate after 30 days

- 10 completed account-specific diagnostics.
- 3 qualified founder conversations.
- 2 human-approved Blueprint proposals.
- 1 paid Blueprint or accepted paid-pilot scope.
- Less than 15 minutes of founder preparation per account.
- Zero unauthorized sends, system writes, unsupported claims, or cross-prospect exposure.

If the conversation and paid-signal gates fail, change the offer or account wedge before buying
more Lovable credits or expanding the application.

## Trade-offs

- A single multi-tenant project is more demanding to secure than separate demos, but it preserves
  credits and produces a reusable conversion surface. Tenant isolation is therefore a release
  gate, not a later enhancement.
- Human approval constrains throughput, but it protects reputation and creates auditable evidence
  for future automation decisions.
- Sanitized data reduces pilot realism, but it avoids exposing prospect or workspace data while
  plan and training-data controls remain unverified.
- Keeping Cloudflare as the public front door adds one handoff, but it avoids replacing the current
  acquisition site and keeps Lovable focused on qualified conversion.

## Open questions

- What renewal year and complete entitlement contract apply to the observed `Lovable Lite`
  US$5/month plan?
- What current AI and Cloud balances and available-funds dates appear in the separate Cloud and AI
  usage surface?
- Has Lovable Support confirmed the Free/Pro training-data opt-out for this workspace?
- Does this account expose the private-project controls and Lovable MCP preview described by the
  cited documentation?
- Which authenticated deep link should the Cloudflare acquisition site use after the first result
  room passes security review?

## Tentative recommendation

Keep the observed Lite plan for one 30-day experiment and spend it only on the bilingual Revenue
Workcell. Treat Lovable as the customer-facing productization and distribution layer between
researched prospects and a human-approved Agent Systems Blueprint. Do not expand credits or scope
until the technical gates pass and the experiment produces qualified conversations plus a paid
signal.
