---
type: article
description: "Canonical approval states, wording, evidence requirements, and review gates for company, customer, product, and investor claims."
status: canonical
supersedes: [ research/investor-claims-and-entity-readiness.md ]
authored: 2026-07-26
author: Lalo, consolidated by Codex
tags: [ article, canonical, claims, marketing, investor, diligence, internal ]
title: Claims registry
sources:
  - research/investor-claims-and-entity-readiness.md
  - external-sources/sites-portfolio-snapshot-2026-07-26.md
  - research/founder-interview-round-4-2026-07-26.md
---

## Summary

This registry is the source of truth for customer-, investor-, partner-, and public-facing claims. A claim is publishable only when its approved wording, evidence, owner, audience, and review date are recorded. Founder-approved target state must not be written as completed legal or commercial fact.

If a deck, site, proposal, social post, case study, directory profile, email, or agent output conflicts with this page, this page wins until the evidence and approval state are updated.

## Claim states

| State | Definition | Allowed use |
|---|---|---|
| Observed | Verified in a dated source/system | State with scope and observation date |
| Founder decision | Approved direction or target state | Use future/intent language; do not imply completion |
| Planned | Proposed but not yet decided or executed | Internal planning only |
| Unverified | Evidence missing, stale, conflicting, or incomplete | Do not publish; create an evidence task |
| Prohibited | Contradicted, misleading, sensitive, or unsupported | Remove or replace before external use |

Every registry row should carry: `claim_id`, approved wording, state, evidence path, observed date, owner, approved audiences, expiry/review date, and superseded wording.

## Canonical claims

### Entity and financing

| Claim | State | Approved wording / treatment |
|---|---|---|
| AE and Curia will raise separately | Founder decision | “Agentic Engineering and Curia are preparing separate financing paths.” Instrument and terms remain unapproved until indexed. |
| Agentic Engineering entity | Founder decision | “Agentic Engineering intends to form a Delaware corporation through Stripe Atlas.” Do not say incorporated until formation evidence exists. |
| Curia entity | Founder decision | “Curia intends to form a Mexican SAPI.” Do not publish RFC, domicile, incorporation, or capitalization until verified. |
| AE owns portfolio IP | Founder decision; execution unverified | “Agentic Engineering intends to own Ultimate Harness, PriceGenius, and Defade IP.” Muta, Agentforge, and SpecSafe remain possible additions. Do not state ownership until assignments and asset schedules are indexed. |
| AE use of Curia/KLGV traction | Prohibited unless explicitly framed as related-founder experience | Curia customer evidence is not AE customer traction. AE investor collateral remediation is tracked in Linear AE-389. |
| ShesMine prior entity/asset references | Unverified | Inventory contracts, IP, liabilities, domains, contributors, and proposed disposition. “Superseded” does not prove obligations or ownership disappeared. |
| Two US$750,000 asks | Unverified current terms | The inspected AE and Curia Sites each showed US$750,000 with different instrument language [source](../external-sources/sites-portfolio-snapshot-2026-07-26.md). Reconfirm each separately before outreach. |

The legal and IP diligence plan lives in [portfolio and platform strategy](./portfolio-and-platform-strategy.md) and [legal entity structure](./legal-entity-structure.md).

### KLGV and Curia

Approved wording:

> KLGV Abogados is Curia’s single current paid design partner. Curia is deployed in pilot use, but is not yet a completed full-production or repeatable commercial deployment.

| Wording | State |
|---|---|
| “Paid design partner” | Approved |
| “Deployed in pilot use” | Approved with the non-production qualifier |
| “Production deployment” | Prohibited today |
| Existing Client Sales deck wording that says “production deployment” | Prohibited in place; corrected-copy work is owned in Linear AE-390. No deployment is authorized in the current batch. |
| Curia investor-deck “deployed” / “first customer” wording without the pilot/non-production qualifier | Unverified or misleading in place; reconciliation is owned in Linear CUR-524. |
| “Production customer” | Prohibited today |
| “Repeatable commercial deployment” | Prohibited today |
| Customer quote, ROI, adoption, metric, screenshot, or case study | Unverified until signed evidence and publication permission are indexed |

The inspected Sites used conflicting KLGV language [source](../external-sources/sites-portfolio-snapshot-2026-07-26.md). All future collateral must use the wording above.

Curia privacy status must also remain qualified: CUR-276 reports that literal placeholders were replaced by interim “entity in formalization” copy, but CUR-277 still lacks independently verified real entity, RFC, domicile, and counsel-approved production wording. Re-verify the live surface before stating either the old placeholder condition or the interim correction is current.

### Multiempaques

| Claim | State | Approved treatment |
|---|---|---|
| Client data is being collected | Founder-reported current state | “Multiempaques is supplying the data needed for the Blueprint.” Add observed date when used. |
| Blueprint price | Founder decision | Free for this engagement as an explicit early-client validation exception. |
| Pricing timing | Founder decision | Price is prepared about 7–10 days after the data-completeness gate is met. |
| Implementation | Conditional | Paid implementation begins only after Multiempaques accepts scope and price. |
| Multiempaques is a paid implementation customer | Prohibited until acceptance/payment evidence exists | Do not imply closed revenue or production delivery. |

### Offer and pricing claims

The current Agentic Engineering reference ladder is free Fit Check → US$4,000 Blueprint → US$8,000/12,000/15,000 bounded pilot → US$2,500/5,000 monthly operations [source](../external-sources/sites-portfolio-snapshot-2026-07-26.md). Use it as reference pricing, not an unconditional quote. Local Mexico eligibility and scope may change pricing with founder approval.

Curia pricing is a separate product motion. Do not mix Curia MXN SaaS pricing with agency USD engagement pricing.

| Curia collateral claim | State | Approved treatment |
|---|---|---|
| MXN 1,250 / 5,800 price points | Unverified current pricing | Treat as internal deck hypotheses until their source, date, scope, founder approval, and canonical pricing-page reconciliation are recorded in CUR-524. |
| Ten paid pilots | Planned milestone, not traction | May appear only as a labeled target; never as achieved customers, current pipeline, or forecast. |
| Current Curia price | Unverified | No public quote until the pricing decision and contracting entity are approved. |

### Pipeline and traction

| Claim | State | Approved treatment |
|---|---|---|
| 50 curated leads / 80 drafts / 50 Twenty records | Self-reported historical artifact; live state unverified | Call it a reported 2026-06 batch artifact. Do not call it observed current pipeline without direct CRM verification of stage, last touch, reply, meeting, owner, and next action. |
| Repository, commit, test, deployment, or deck count | Observed product evidence | Use as execution proof, not customer demand or revenue. |
| Current replies, meetings, proposals, CAC, LTV, retention, churn | Unverified | Do not publish until source-of-truth metrics exist. |
| Héctor Guerra work | Existing client evidence in current wiki | Keep separate from Curia traction and investor proof unless explicitly approved. |

### ICP and market-positioning claims

| Claim | State | Approved treatment |
|---|---|---|
| AE services primary ICP: operationally complex Mexican mid-market companies | Current canonical operating hypothesis | Use for the first 50-account segment; it is a focus decision, not proof of market demand. |
| Regulated U.S. mid-market, 50–499 employees | Unverified investor-deck positioning | Do not replace the current Mexico-primary ICP or publish as validated focus until founders reconcile segment, geography, proof, and economics. Remediation is tracked in AE-389. |
| AE platform ICP: product teams with material agent workloads and measurable failure/economic data | Current canonical operating hypothesis | Qualify by production task volume, task metric, failure examples, economic value, and implementation authority. |

### Model and platform claims

| Claim | State | Approved treatment |
|---|---|---|
| SceneSpec score/latency | Observed narrow benchmark | May state with exact harness scope and date. |
| Opus/Sol/Kimi ranking on SceneSpec | Observed narrow benchmark | Do not transfer to sales or general intelligence. |
| 98% sales-harness schema-validity gate | Prospective promotion threshold | SceneSpec did not test the sales corpus and does not prove this threshold has been met. |
| AE router can become better than any constituent model on validated tasks | Founder decision / thesis | State as the platform objective. |
| AE router is already universally superior | Prohibited | Requires task-specific evaluation and production evidence. |

See [model routing and sales harness](./model-routing-and-sales-harness.md).

### Market and economics

| Claim | State | Approved treatment |
|---|---|---|
| US$988M–1.98B | Unverified as TAM | If retained, label a modeled recurring-workflow spend envelope with assumptions—not proven TAM, SAM, revenue, or contracted demand. |
| Customer ROI or savings | Unverified by default | Requires dated before/after method, denominator, exclusions, customer approval, and evidence. |
| Gross margin/contribution | Unverified until instrumented | Define realized delivery cost, model/tool cost, founder labor treatment, and exclusions. |

## Audience controls

| Audience | Rule |
|---|---|
| Public | Only approved wording and non-sensitive evidence with publication permission |
| Prospect | Public claims plus account-specific evidence; no investor-only or confidential customer data |
| Customer | Contract- and project-specific facts; no cross-customer data |
| Investor | Public claims plus private diligence evidence approved for investor disclosure |
| Internal | May include unverified hypotheses when labeled; secrets and personal data remain access-controlled |

## Review gate

Before any external artifact or send:

1. Extract each material claim.
2. Match it to a registry row.
3. Verify evidence and review date.
4. Check audience permission and customer consent.
5. Replace or remove conflicting wording.
6. Obtain the named human approver.
7. Store the final artifact and claim disposition.

Agents may flag and draft corrections. They do not approve their own customer or investor claims.

## Evidence needed next

- Formation and tax records for each entity.
- Cap table and financing instrument for each separate raise.
- Founder invention and IP assignments; asset ownership schedule.
- Signed KLGV contract/payment and publication permissions.
- Multiempaques data-completeness, proposal, acceptance, and payment evidence.
- Live CRM funnel state and metric definitions.
- Realized engagement economics and recurring-product cohort evidence.
- Task-specific model-harness results.

## References

- [Investor claims and entity readiness research](../research/investor-claims-and-entity-readiness.md)
- [Sites portfolio snapshot](../external-sources/sites-portfolio-snapshot-2026-07-26.md)
- [Founder interview — Round 4](../research/founder-interview-round-4-2026-07-26.md)
- [Marketing honesty policy](./marketing-honesty-policy.md)
- [Founder-led growth operating system](./founder-led-growth-operating-system.md)
