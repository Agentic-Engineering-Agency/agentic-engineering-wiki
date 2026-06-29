---
description: SpecSafe = open methodology + agency differentiator; not commercial product.
sources:
  - research/founder-interview-round-3-2026-06-26.md
status: canonical
tags:
  - specsafe
  - open-source
  - methodology
  - canonical
  - internal
title: SpecSafe — product thesis
---
# SpecSafe — product thesis

Internal canonical. Resolves [OSS golden path tension](./oss-golden-path-decision.md) for **methodology**; harness repo consolidation remains separate.

## Decision (2026-06-26)

**SpecSafe = methodology, not commercial product.**

| Path | Status |
| --- | --- |
| Commercial OSS / hosted gates in 12 months | **Rejected** (not 28A) |
| Open core forever; agency delivery differentiator | **Selected** (28B) |
| Merge into ultimate-harness / omp-pantheon as product surface | **Rejected** for SpecSafe brand (28C/D) |

## What SpecSafe is

A **skills-first framework** keeping AI coding agents aligned with human intent — specifications, TDD, QA gates ([public claim](../external-sources/agenticengineering-agency-site.md): 8 tools, 3 integration tiers).

**Job in the business:**

1. **Delivery credibility** — clients see spec+TDD discipline, not demo agents ([company identity](./company-identity.md)).
2. **Open-source wedge** — AI-TDD narrative for inbound ([open source strategy](./open-source-strategy.md)).
3. **Internal enforcement** — how we build Curia and agency deliverables ([delivery process](./delivery-process.md)).

## What SpecSafe is not

- Primary revenue SKU (Curia SaaS is product bet)
- License/support business in 2026
- Replacement for [Mastra](https://mastra.ai) / harness runtime — SpecSafe governs **how** agents change code, not orchestration graphs

## Harness repos (still messy)

SpecSafe direction ≠ harness **golden path** repo. Overlapping repos (ultimate-harness, omp-pantheon, pi-seshat, agentforge) still need **cull/consolidation** — see [open source strategy](./open-source-strategy.md).

**Working rule:** SpecSafe = public methodology story; pick **one** harness repo later for contributor code paths only.

## Success metrics (2026)

- Used on every agency + Curia slice with documented gate
- ≥1 inbound conversation citing SpecSafe / AI-TDD (track attribution)
- No new harness repo without archiving old one

## Related

- [Open source strategy](./open-source-strategy.md)
- [OSS golden path decision (OPEN)](./oss-golden-path-decision.md) — harness only
- [Delivery process](./delivery-process.md)