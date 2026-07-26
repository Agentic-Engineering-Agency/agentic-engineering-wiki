---
type: source
description: "Point-in-time local benchmark record for strict SceneSpec generation quality, validity, and latency."
source_url: https://github.com/Agentic-Engineering-Agency/prism-arena
date_fetched: 2026-07-26
preservation: text-extracted
tags: [ source, immutable, layer-ingest, text, models, benchmark ]
title: Prism SceneSpec benchmark snapshot — 2026-07-26
source_type: local-sqlite-and-config-audit
observed_at: 2026-07-26
---

## Capture method

Read-only inspection of `prism-arena/config/models.json` and `prism-arena/data/prism-arena.sqlite` on 2026-07-26. No benchmark runs, model calls, repository edits, or database writes were performed for this snapshot.

The judged score uses ten runs per model evaluated by four model judges. Validity uses twenty executions per model.

## Recorded results

| Router label | Valid executions | Mean judged score / 20 | Mean latency |
|---|---:|---:|---:|
| Claude Opus 5 | 20 / 20 | 18.38 | 159 s |
| GPT-5.6 Sol | 20 / 20 | 17.82 | 111 s |
| Kimi K3 | 18 / 20 | 17.77 | 288 s |
| Claude Fable 5 | 20 / 20 | 17.32 | 141 s |
| GPT-5.6 Terra | 19 / 20 | 16.68 | 87 s |
| GPT-5.6 Luna | 19 / 20 | 15.93 | 102 s |
| Gemini 3.6 Flash | 19 / 20 | 15.03 | 234 s |

## Scope limits

This benchmark tested strict 3D `SceneSpec` adherence, route validity, and latency under one local harness. It did not test lead discovery, enrichment accuracy, ICP scoring, persuasive writing, meeting preparation, proposal quality, objection handling, asset performance, or revenue outcomes. Model-judge scoring does not eliminate judge bias. Router labels may not be stable public model identities.
