---
description: "Open decision: which OSS repo is the external golden path."
sources:
  - research/founder-interview-round-2-2026-06-26.md
status: canonical
tags:
  - open-source
  - decision
  - internal
  - todo
title: OSS golden path — decision (OPEN)
---
> [!NOTE]
> **SpecSafe direction decided (R3 28B):** [methodology / open core forever](./specsafe-product-thesis.md) — **not** a commercial product.
>
> **Harness golden path: still OPEN** (R2 18D). Do not point external contributors at multiple harness repos.

## Problem

21 public repos; overlapping harness/agent frameworks. Maintenance cost on **2-person team** is unsustainable without a **single golden path**.

## Candidates

| Repo | Pros | Cons |
| --- | --- | --- |
| **SpecSafe** | Clear wedge (AI-TDD); marketing story | Ambition TBD (product vs methodology) |
| **ultimate-harness** | "One harness, every agent" narrative | Overlap with omp-pantheon, pi-seshat |
| **omp-pantheon** | Most integrated (SpecSafe, Honcho, EvalFly) | Heavy; may be internal-only complexity |
| **agentforge** | Mastra + hosting story | README says Convex; Curia uses **Turso** |
| **pi-seshat** | Pi-specific niche | Narrow audience |

## Decision criteria (draft)

1. Aligns with [delivery differentiation](./company-identity.md) (spec + eval)
2. Minimal overlap with Curia eng bandwidth
3. Can explain in one README in <5 min
4. Inbound lead attribution measurable within 6 months

## Actions when decided

- [ ] Pick golden path repo
- [ ] Archive or mark `experimental` on non-path harness repos
- [ ] Update [agency site](../external-sources/agenticengineering-agency-site.md) OSS section to match
- [ ] Link from [open source strategy](./open-source-strategy.md)

## Related

- [Open source strategy](./open-source-strategy.md)
