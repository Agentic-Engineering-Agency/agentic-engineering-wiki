---
type: source
description: "Read-only audit record for five Agentic Engineering, Curia, Multiempaques, and MemSWE Sites projects."
source_url: https://agenticengineering.chatgpt.site
date_fetched: 2026-07-26
preservation: text-extracted
tags: [ source, immutable, layer-ingest, text, sites, portfolio ]
title: Sites portfolio snapshot — 2026-07-26
source_type: live-sites-connector-audit
observed_at: 2026-07-26
---

## Capture method

Read-only Sites connector inspection plus authenticated rendering of five user-specified projects on 2026-07-26. No source edits, versions, deployments, access changes, domain changes, or deletion were performed.

## Project observations

| Project | Saved state | Access observed | Content observations |
|---|---|---|---|
| `appgprj_6a6287818d2c8191b1216d349d848225` — Multiempaques · Prep 30 | Active; version 1; source SHA `6b7b45d` | Custom owner-only; no custom domain observed | Private 30-minute Aspel-SAE discovery guide with audio, visual route, checklist, and PDF/DOCX/TXT downloads. No durable CRM/account handoff or proposal-tracking surface was observed in the rendered project. |
| `appgprj_6a50250533dc819188d073395072cf89` — MemSWE · Resultados PAP 2026 | Active; version 9; source SHA `aeb6e8c` | Custom owner-only; no custom domain observed | Reports 360 runs, 15 tasks, 6 conditions, and 4 repetitions; explicitly avoids unsupported leaderboard claims. No Agentic Engineering contact path or commercial CTA was observed. |
| `appgprj_6a541ebbad34819190dd7db354467c31` — Agentic Engineering · Client Sales | Active; version 2; source SHA `860596c` | Custom owner-only; no custom domain observed | Offer ladder shown as free Fit Check, US$4,000 Blueprint, US$8,000/12,000/15,000 pilots, and US$2,500/5,000 monthly operations. The CTA href targeted `agenticengineering.agency/#workflow-fit-check`. The deck described KLGV as a production deployment. |
| `appgprj_6a541ec349cc8191b7726f7e29d6c78f` — Agentic Engineering · Investor Overview | Active; version 4; source SHA `338cdd0` | Custom owner-only; no custom domain observed | Positions a Production Layer for regulated U.S. mid-market firms, cites Mexico design-partner proof, states repeatability is unproven, and shows a US$750,000 SAFE ask. Email was the only CTA observed. |
| `appgprj_6a5683dbf5108191bc40a8e9eb5791f9` — Curia · Investor Deck | Active; version 1; source SHA `013fa21` | Custom owner-only; no custom domain observed | Positions court intelligence for Mexican firms, cites KLGV, shows MXN 1,250 and MXN 5,800 SaaS pricing, a 10-paid-pilot milestone, and a US$750,000 SAFE or convertible-note ask. It used “deployed,” “real deployed platform,” and “first customer” wording. A `curia.mx` text link resolved to a Workers domain in the inspected build. |

## Cross-document observations

- The projects used inconsistent KLGV descriptions: “production deployment,” “pilot / not full production,” and “deployed / first customer.”
- The Agentic Engineering and Curia investor projects each showed a US$750,000 raise while using different instrument wording.
- The Agentic Engineering project targeted U.S. regulated firms with 50–499 employees; the Curia project focused on smaller Mexican firms.
- Agency engagement pricing was denominated in USD; Curia SaaS pricing was denominated in MXN.
- All five projects were owner-only at the time of inspection.

## Limits

The connector exposed active project and saved-version metadata but not enough deployment identity to prove which saved version was serving production. A rendered link or CTA was observed, not submitted. Absence of a CRM, form, scheduler, or analytics surface in these renders does not prove it is absent elsewhere.
