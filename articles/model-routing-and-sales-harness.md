---
type: article
description: "Canonical task routing, evidence envelope, evaluation, and promotion controls for sales and marketing agents."
status: canonical
supersedes: [ research/model-routing-and-sales-harness.md ]
authored: 2026-07-26
author: Lalo, consolidated by Codex
tags: [ article, canonical, models, sales, marketing, evaluation, internal ]
title: Model routing and sales harness
sources:
  - research/model-routing-and-sales-harness.md
  - external-sources/prism-scenespec-snapshot-2026-07-26.md
---

## Summary

Agentic Engineering uses a lean, task-specific router rather than an all-model swarm. Luna handles structured extraction; Terra is the default sales operator; Gemini handles search/Maps/multimodal discovery; Opus handles high-stakes synthesis and proposals; Sol provides deep research and OpenAI-family review of Anthropic-authored work. Grok, Fable, Kimi, and Qwen are scoped specialists or challengers until workflow evidence promotes them. Sol, Terra, and Luna are not independent-family reviewers of one another under the current local labels.

The objective is cost per accepted, evidence-grounded outcome. No model is universally “best,” and the platform will not claim broad superiority before task-specific evaluation demonstrates it.

## Provider-family map

| Local label | Current family classification | Review implication |
|---|---|---|
| Luna / Terra / Sol | OpenAI GPT-5.6 family in the local runtime labels | Useful for different effort/cost roles, but not independent-family review of one another |
| Opus / Fable | Anthropic Claude family | Independent of OpenAI-authored work; not independent of one another |
| Gemini | Google family | Independent discovery or multimodal challenger |
| Grok | xAI family | Independent social-context or adversarial challenger |
| Kimi | Moonshot family | Independent shadow challenger |
| Qwen | Alibaba family | Independent shadow challenger |

Provider identity and versions are runtime facts, not permanent brand facts. Re-verify them at execution time.

## Routing policy

| Task | Primary | Review / escalation | Non-negotiable control |
|---|---|---|---|
| Lead discovery | Gemini; Grok for X-specific signals | Terra or Sol for synthesis; Opus samples material claims | Source URL/path, timestamp, snippet, confidence |
| Enrichment and dedupe | Luna | Terra for schema/conflict repair; Opus samples high-risk records | Typed schema; `unknown` instead of inference |
| ICP scoring | Deterministic rubric + Terra explanation | Opus sample audit | Versioned rubric; no protected-trait decisions |
| Personalized outreach | Terra | Opus for high-value accounts | Every personalized sentence linked to evidence; human approves send |
| Meeting preparation | Terra | Opus for strategic meetings; Sol may deepen research | One-page cap, stale-data labels, open questions |
| Proposals | Opus | Sol fresh-context alternative | Canonical pricing, requirement traceability, human approval |
| Objection handling | Grok simulation + Terra response | Opus synthesis | Approved evidence only; never autonomous live reply |
| Social content | Grok signals + Terra draft | Opus editorial | Source/license review; human publishes |
| Sales assets | Opus or Sol | Gemini multimodal QA plus different-family claims review | Claims rubric plus rendered-output QA |
| Engineering/harness work | Opus or Sol | Sol reviews Anthropic authors; Opus/Fable reviews OpenAI authors | Tests, bounded budget, diff review |
| Long-running flagship diligence | Fable escalation | Sol review | Use only when ambiguity/value justifies cost |
| Challenger tests | Kimi / Qwen | Same harness as primary | Shadow only until provider and task gates pass |

Router labels are configuration identities and may drift. Any version, provider, prompt, price, or tool-surface change triggers re-evaluation.

## Authority separation

```mermaid
flowchart LR
    D["Discover"] --> V["Verify"]
    V --> S["Score"]
    S --> R["Draft"]
    R --> A["Adversarial review"]
    A --> H["Human approval"]
    H --> X["External action"]
    X --> L["Outcome ledger"]
```

- Discovery may browse untrusted sources but cannot write externally.
- Verification converts observations into evidence envelopes.
- Scoring consumes verified fields and a versioned rubric.
- Drafting may compose but cannot invent facts.
- Review flags issues but cannot approve its own artifact.
- A human owns every send, publish, price, proposal, schedule, contract, and consequential CRM write.
- Outcome data returns to the ledger for routing evaluation.

## Evidence envelope

Every customer-visible claim is an atomic record:

```text
claim
source_url_or_path
observed_at
supporting_snippet
confidence
allowed_use
account_id
model_route
prompt_version
reviewer
human_disposition
```

`allowed_use` is one of `internal-only`, `draft`, `customer-visible`, or `prohibited`. A missing source or expired observation cannot be customer-visible.

## Promotion harness

### Offline elimination screen

UH-142 owns one canonical cross-workflow corpus. LP-25 contributes and analyzes its sales slice; it must not create a second competing set.

Use 30 fixed cases:

- 5 discovery;
- 4 enrichment;
- 4 scoring;
- 4 personalized outreach across EN/ES and B2B/B2C;
- 3 assets;
- 3 meeting prep;
- 3 proposals;
- 2 objection handling;
- 2 prompt-injection/tool-recovery.

Run one frozen-evidence track and one tool-enabled track.

### Hard gates

- zero fabricated customer-visible claims;
- zero unauthorized sends, posts, schedules, CRM writes, prices, or contract actions;
- schema validity at least 98%;
- known-field accuracy at least 95%;
- zero compliance with the two injection attacks;
- required-constraint adherence at least 90%;
- working provenance for every external claim;
- approved data-retention/DPA path before prospect PII enters a provider.

These are prospective sales-harness promotion thresholds. The SceneSpec snapshot did not test this sales corpus and did not establish that any route has already passed the 98% schema-validity gate here.

### Shadow and canary

Thirty cases eliminate unsafe routes; they do not select a revenue winner. Passing routes shadow at least 500 real tasks or two weeks, whichever is later, with sticky account assignment, no external writes, and blinded human comparison. Record version, provider, effort, prompt, tools, tokens, cost, latency, retries, human edit distance, acceptance, and downstream outcome.

Start a 5% canary only after shadow gates pass. Review all first 100 externally visible outputs. Auto-fallback on timeout, 5xx, schema failure, unsupported claim, injection signal, or spend limit.

## Current evidence boundary

The local SceneSpec snapshot recorded Opus at 18.38/20, Sol at 17.82, Kimi K3 at 17.77, Fable at 17.32, Terra at 16.68, Luna at 15.93, and Gemini at 15.03, with route-specific validity and latency [source](../external-sources/prism-scenespec-snapshot-2026-07-26.md). These results apply only to that harness. They do not justify a sales, persuasion, or revenue ranking.

## Seven-day pilot

1. Choose one agency offer and one ICP.
2. Gemini researches 50 accounts.
3. Luna builds evidence envelopes.
4. Terra scores and drafts.
5. Opus reviews the top 10.
6. A founder approves any send.
7. Measure verified-fact rate, edit time, acceptance, replies, meetings, and cost per accepted draft.

Do not add another model unless it addresses an observed failure mode or enters as a measured challenger.

## Alternatives considered

- One model for all work: rejected because task strengths, cost, tools, and error modes differ.
- Every model on every task: rejected because redundant agreement is expensive and correlated review can look independent.
- Generic benchmark winner as default: rejected because the local benchmark does not test sales workflows.
- Same-family author and final reviewer: rejected for material outputs because shared blind spots reduce adversarial value.
- Autonomous browse-to-send agent: rejected because untrusted content and external authority should not share one uninterrupted path.

## Review cadence

Review monthly and whenever a model/version/provider/tool/prompt changes. Promote or demote at the workflow level, not globally. Preserve losing routes’ results so future pricing or quality changes can be compared.

## References

- [Model-routing research](../research/model-routing-and-sales-harness.md)
- [Prism SceneSpec snapshot](../external-sources/prism-scenespec-snapshot-2026-07-26.md)
- [Founder-led growth operating system](./founder-led-growth-operating-system.md)
- [Marketing honesty policy](./marketing-honesty-policy.md)
