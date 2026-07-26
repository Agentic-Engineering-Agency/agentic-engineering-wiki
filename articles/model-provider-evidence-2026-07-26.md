---
type: evidence-note
title: Model provider evidence — 2026-07-26
description: Official provider facts, local route distinctions, known staleness, and safe claim boundaries for the Agentic Engineering sales router.
status: current
observed: 2026-07-26
author: Codex with fresh cross-family review
tags: [models, providers, routing, evidence, sales, internal]
---
# Model provider evidence — 2026-07-26

## Conclusion

Every scoped product is currently confirmed by an official provider source, but none has official evidence of better conversion, persuasion, or revenue performance. Provider positioning is a routing prior, not a sales benchmark. Agentic Engineering must promote a route only after it passes the sales-specific harness in [Model routing and sales harness](./model-routing-and-sales-harness.md).

A model product, a deployment route, and an independent provider family are different facts. Record all three. A route can be useful without being suitable as an independent reviewer.

## Official facts and safe test roles

| Product | Official fact observed 2026-07-26 | Safe role to test | Boundary |
|---|---|---|---|
| Claude Opus 5 | Anthropic documents `claude-opus-5`, a 1M-token context window, and positioning for complex agentic and enterprise work [release](https://www.anthropic.com/news/claude-opus-5), [API notes](https://platform.claude.com/docs/en/about-claude/models/whats-new-opus-5) | High-stakes proposals, strategy, final QA of non-Anthropic work | Role is an inference; no sales-performance proof |
| Claude Fable 5 | Anthropic documents `claude-fable-5`, demanding long-horizon work, restored access, and a 30-day retention requirement [introduction](https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5), [product](https://www.anthropic.com/claude/fable), [redeployment](https://www.anthropic.com/news/redeploying-fable-5) | Rare flagship diligence after privacy review | Same Anthropic family as Opus; avoid prospect PII until retention/DPA is accepted |
| GPT-5.6 Sol | OpenAI positions Sol as the frontier-capability tier; the `gpt-5.6` alias routes to Sol [guidance](https://developers.openai.com/api/docs/guides/latest-model), [release](https://openai.com/index/gpt-5-6/) | Strategic synthesis and different-family review of Anthropic-authored work | No sales-performance proof |
| GPT-5.6 Terra | OpenAI positions Terra as the capability/cost balance [guidance](https://developers.openai.com/api/docs/guides/latest-model) | Default coordination and drafting candidate | Outreach quality remains a harness hypothesis |
| GPT-5.6 Luna | OpenAI positions Luna as the efficient high-volume tier [guidance](https://developers.openai.com/api/docs/guides/latest-model) | Extraction, classification, dedupe | Schema accuracy remains unproven on the sales corpus |
| Kimi K3 | Moonshot documents `kimi-k3`, 1M context, native vision, and long-horizon coding/knowledge work; the API omits some app-only PPT/deep-research surfaces [model selection](https://www.kimi.com/help/kimi-api/api-model-selection) | Large evidence-corpus synthesis challenger | Verify route price and release state at execution time; do not claim lower cost from memory |
| Grok 4.5 | xAI documents `grok-4.5` for knowledge and agentic work; cited X Search is a separate enabled tool [release](https://x.ai/news/grok-4-5), [X Search](https://docs.x.ai/developers/tools/x-search) | X-specific signal discovery when the tool is enabled; independent challenge | Do not imply every Grok route has live X access or superior objection handling |
| Cursor Composer 2.5 | Cursor documents a Cursor-only coding model for sustained long-running coding and background agents [product](https://cursor.com/composer), [release](https://cursor.com/blog/composer-2-5) | Build and maintain sales harnesses, integrations, and landing pages | No official basis for sales-copy or persuasion superiority |
| Cursor Grok 4.5 | Cursor documents a broader first-party Grok 4.5 route for software and knowledge work [overview](https://cursor.com/grok-4-5), [release](https://cursor.com/blog/grok-4-5) | Fresh-family read-only challenge and implementation review | Record Cursor route, tools, effort, and version separately from xAI API use |
| Sakana Fugu Ultra | Sakana documents dynamic one-to-three-agent orchestration through a fixed, undisclosed pool [release](https://sakana.ai/fugu-release/), [models](https://console.sakana.ai/models), [pricing](https://console.sakana.ai/pricing) | Experimental escalation for difficult public-data diligence | Not an independent provider-family reviewer; hidden pool and data terms must pass review |

## Local evidence boundary

- [Prism SceneSpec snapshot](../external-sources/prism-scenespec-snapshot-2026-07-26.md) measures SceneSpec quality, validity, latency, and route-specific behavior only. It is not a sales ranking.
- `prism-arena/config/models.json` contains local OMP route IDs such as `openai-codex/gpt-5.6-sol`, `anthropic/claude-opus-5`, and `cloudflare-ai-gateway/moonshotai/kimi-k3`. These are not necessarily official API model IDs.
- `factory-research/docs/pages/models.md` is stale on Fable availability: it records unavailability after June 12; Anthropic says access was restored July 1. Runtime health still needs execution-time verification.
- Cursor discloses that an earlier CursorBench used a prior Cursor codebase snapshot. Do not use that benchmark for comparative superiority claims.

## Independent-review rule

- OpenAI Sol/Terra/Luna are one family for review-independence purposes.
- Anthropic Opus/Fable are one family.
- Cursor Grok 4.5 and xAI Grok 4.5 share a named model lineage even though deployment surfaces differ.
- Fugu Ultra's undisclosed pool cannot prove independence from the authoring family.
- A materially consequential artifact needs a reviewer whose provider family is known and differs from the authoring model, plus deterministic checks where available.

## Safe external language

> Current provider documentation positions Sol for frontier work, Terra for balanced everyday workloads, and Luna for efficient high-volume work. Agentic Engineering treats those descriptions as routing priors and promotes routes only through sales-specific evaluations.

> Grok 4.5 can be paired with xAI's X Search tool for cited social-signal research when that tool is explicitly enabled.

> No current model has yet demonstrated a conversion or revenue advantage on Agentic Engineering's sales corpus.

Avoid: “Opus is best for sales,” “Kimi is equally capable for less,” “Fugu provides independent multi-vendor review,” “Grok always has live X access,” or “our router automatically selects the best model.”