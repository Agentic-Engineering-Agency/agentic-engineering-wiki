---
type: research-note
title: Twenty CRM to OmniRoute provider contract
description: Provisional least-privilege contract for a self-hosted Twenty custom AI provider backed by OmniRoute.
status: provisional
created: 2026-08-10
checked: 2026-08-10
author: Codex
confidentiality: internal
cluster: model-routing
tags:
  - research
  - provisional
  - twenty-crm
  - omniroute
  - ai-provider
  - security
sources:
  - https://docs.twenty.com/user-guide/ai/how-tos/ai-faq
  - https://docs.twenty.com/user-guide/ai/capabilities/permissions-access-control
  - https://github.com/twentyhq/twenty/blob/0ef79db84202e333fb6007347590294793a88d83/packages/twenty-server/.env.example
  - https://github.com/twentyhq/twenty/blob/0ef79db84202e333fb6007347590294793a88d83/packages/twenty-server/src/engine/metadata-modules/ai/ai-models/services/ai-model-registry.service.ts
  - https://github.com/twentyhq/twenty/blob/0ef79db84202e333fb6007347590294793a88d83/packages/twenty-server/src/engine/metadata-modules/ai/ai-models/services/provider-config.service.ts
  - https://github.com/twentyhq/twenty/blob/0ef79db84202e333fb6007347590294793a88d83/packages/twenty-server/src/engine/metadata-modules/ai/ai-models/services/sdk-provider-factory.service.ts
  - https://github.com/twentyhq/twenty/blob/0ef79db84202e333fb6007347590294793a88d83/packages/twenty-server/src/engine/metadata-modules/ai/ai-models/types/ai-provider-config.schema.ts
---

## Decision boundary

The smallest safe design is one self-hosted Twenty custom provider named `omniroute`, one manually
declared canary model, and one new OmniRoute inference-only key. The provider uses the
OpenAI-compatible base `https://omniroute.agenticengineering.lat/v1`; the key allows only the
selected model and the `chat` endpoint category. Model discovery, Responses, tools, images,
autonomous writes, and `auto/*` routes stay disabled until separately approved.

This is a design and approval record. It does not authorize a key, provider, routing, deployment,
license purchase, or model call. It is internal under the
[[articles/public-wiki-boundary|Public wiki boundary]] and does not establish a publishable model
or platform claim under the [[articles/claims-registry|Claims registry]].

## Current evidence state

| Observation | Evidence state | Contract consequence |
| --- | --- | --- |
| Twenty documents AI Chatbot and workflow AI Agents, with roles limiting the data and actions an agent may access. | Observed in official Twenty docs on 2026-08-10. | Assign the canary agent a dedicated read-only role over only the pilot object/fields. |
| Twenty Cloud does not accept custom models; a self-hosted instance needs an Organization license to use them. | Observed in the official [AI FAQ](https://docs.twenty.com/user-guide/ai/how-tos/ai-faq) on 2026-08-10. | License and self-hosted edition confirmation are hard gates. |
| Current Twenty source supports custom providers through `@ai-sdk/openai-compatible`, requires a base URL, and passes the bare configured model name to that provider. | Observed at Twenty commit [`0ef79db`](https://github.com/twentyhq/twenty/tree/0ef79db84202e333fb6007347590294793a88d83) on 2026-08-10. | Use the `/v1` base once and preserve OmniRoute's exact model ID as the bare model name. |
| An unauthenticated BrowserOS neo read of `/v1/models` returned `AUTH_002` / `Authentication required`. | Observed live on 2026-08-10; no credential or inference request used. | The endpoint exists and fails closed, but this did not verify the authenticated catalog. |
| A goal-Coordinator read-only live inspection reported OmniRoute v3.8.49, 1,157 models for both Chat Completions and Responses, four existing all-model keys with no budget, and no Twenty-specific key. | Forwarded live evidence received 2026-08-10; not independently reproduced in this task because the BrowserOS session was at the login gate. | Do not reuse an existing key. A new bounded key is mandatory. Treat counts as a snapshot, not an API contract. |
| Machine-local OMP config already uses the same `/v1` base with `openai-completions`; its 2026-08-10 cache held 1,699 entries. | Confirmed locally, but cached rather than live. | The 1,699-versus-1,157 mismatch proves that model availability must be refreshed immediately before approval. |
| Installed OmniRoute v3.8.46 source distinguishes management tokens from inference keys and exposes per-key model, endpoint, expiry, rate, budget, and token controls. | Confirmed from installed source; the live service reports the newer v3.8.49. | Use only controls confirmed in the live v3.8.49 UI when the key is created; never copy a management credential. |

The existing [[articles/model-routing-and-sales-harness|Model routing and sales harness]] remains the
canonical rule for promotion: route labels are hypotheses until workflow-specific evidence earns a
canary.

### Later live configuration evidence

After the design pass, the founder created a dedicated OmniRoute provider entry through Twenty's
admin UI. A read-only database-shape check confirmed one workspace-global `AI_PROVIDERS` entry
named `omniroute` with a label and base URL, but no declared models; no secret value was printed or
copied into the repository. Twenty `2.26.1` appears to store this sensitive JSON without encrypting
the nested API key, so migration to an environment-backed external catalog remains a security
task. Do not substitute a broader server key for the dedicated CRM key.

An authenticated read-only catalog check confirmed `aug/gpt5.6-sol`, but sanitized completion
canaries did not earn promotion: `aug/gpt5.6-sol` returned 502,
`azure-ai/gpt-5.6-sol-2026-07-09` returned 404, and `oc/gpt-5.6-sol` returned 403. No custom
OmniRoute model was therefore added to Twenty's provider entry or selected as a default. The
working admin default was set to Twenty's built-in `GPT-5.6 Sol` smart model; `GPT-5 Mini` remains
the fast model. This is a containment choice, not proof that the OmniRoute contract is complete.

## Twenty provider contract

### Logical configuration

| Field | Required value | Reason |
| --- | --- | --- |
| Twenty provider key | `omniroute` | Stable namespace for composite model IDs. |
| SDK package | `@ai-sdk/openai-compatible` | Current Twenty source's custom-provider path. |
| Base URL | `https://omniroute.agenticengineering.lat/v1` | The SDK appends the OpenAI operation path; using the root omits `/v1`, while appending another `/v1` would double-prefix requests. |
| Authentication | `Authorization: Bearer <dedicated inference key>` | OmniRoute inference contract; management/session credentials are out of scope. |
| Upstream model name | One exact OmniRoute model ID, initially proposed as `azure-ai/gpt-5.6-luna` | The bare model name is sent to OmniRoute. This ID is locally cached evidence and still needs authenticated live confirmation. |
| Twenty composite model ID | `omniroute/azure-ai/gpt-5.6-luna` | Twenty builds IDs as `providerKey/modelName`; this is the ID used for defaults and workspace preferences. |
| Endpoint | OpenAI Chat Completions under `/v1`; allow OmniRoute category `chat` only | Smallest path supported by the local clients and installed gateway source. Responses is not needed for the first canary. |
| Modalities | Text input and text output only | Avoids unverified image/audio/tool compatibility and unnecessary data exposure. |
| Model registration | Manual one-model `models` entry | Twenty registers no models when a provider's `models` list is empty; manual declaration removes the need to grant `models` discovery to the inference key. |

Twenty's source makes a crucial distinction: `azure-ai/gpt-5.6-luna` is the bare upstream name,
while `omniroute/azure-ai/gpt-5.6-luna` is Twenty's composite registry ID. Sending the composite ID
to OmniRoute would incorrectly add a provider prefix.

### OpenAI-compatible assumptions to prove

| Assumption | Evidence now | Required proof |
| --- | --- | --- |
| Twenty's OpenAI-compatible adapter calls Chat Completions and accepts OmniRoute's response/stream shape. | Twenty constructs `@ai-sdk/openai-compatible`; local OmniRoute clients use Chat Completions. | One sanitized canary after paid-call approval, including streaming off and on if Twenty uses both. |
| The model accepts the roles Twenty emits. | Local cache samples say the candidate does not support the OpenAI `developer` role. | Capture a redacted outbound shape or run a stub compatibility test; permit only `system`, `user`, and `assistant` until proven otherwise. |
| Tool calls are compatible. | Unverified. | Keep workflow tools and autonomous agents disabled; test separately before enabling any tool schema. |
| Usage fields are returned in a shape Twenty can meter. | Unverified; cached zero cost is not proof of free service. | Confirm token usage on an approved canary and reconcile it with OmniRoute key usage. |
| Model ID remains routable. | Candidate is in a dated local cache; forwarded live evidence gave only catalog counts. | Authenticated read-only catalog check immediately before key creation and again before canary. |

The first feature should be a bounded, read-only summarization or classification step over sanitized
test data. AI Chatbot over the whole workspace, autonomous workflow actions, emails, record updates,
and external HTTP tools are later scopes.

## Model IDs and freshness

| Gateway model ID | Twenty composite ID | Proposed status |
| --- | --- | --- |
| `azure-ai/gpt-5.6-luna` | `omniroute/azure-ai/gpt-5.6-luna` | One-model canary candidate; live confirmation required. |
| `azure-ai/gpt-5.6-terra` | `omniroute/azure-ai/gpt-5.6-terra` | Optional smart route only after the first canary and separate model approval. |
| `azure-ai/gpt-5.6-sol` | `omniroute/azure-ai/gpt-5.6-sol` | Optional high-cost/high-stakes route; not part of the initial key. |
| `azure-ai/DeepSeek-V4-Flash` | `omniroute/azure-ai/DeepSeek-V4-Flash` | Challenger only; historical committed clients used a different prefix and case, so exact live verification is mandatory. |
| `auto/best-free`, `auto/cheap`, or `auto/chat` | `omniroute/<auto-route>` | Explicitly out of scope. An alias can change its concrete provider/model without a Twenty config change. |

Freshness state is part of the contract:

- `confirmed-live`: model returned by an authenticated read-only catalog check at approval time;
- `cached-current-day`: present only in a dated local cache; eligible for review, not activation;
- `forwarded-live-summary`: reported by another live inspection without an independently captured
  model ID;
- `stale-or-conflicting`: prefix, case, count, version, or capability differs across sources;
- `unknown`: no current primary evidence.

Only `confirmed-live` may enter the key allowlist. A catalog count never substitutes for the exact
ID and capability check.

## Secret and least-privilege contract

The OmniRoute credential belongs only in the Twenty server's deployment secret surface. It must
not appear in committed JSON/YAML, browser code, workflow payloads, CRM fields, prompts, logs,
screenshots, support exports, or user-facing errors. Twenty's current source supports server-side
`AI_PROVIDERS`, but custom provider values deliberately do not expand nested `{{VAR}}` templates.
Therefore, inject the complete secret-bearing value through the deployment secret manager, or use
the Twenty admin provider surface only after its at-rest storage and redaction behavior are
verified. Do not place a placeholder in committed provider JSON and assume Twenty will resolve it.

Create a dedicated inference key with all of these non-empty controls:

| Control | Pilot proposal |
| --- | --- |
| Owner/label | `twenty-crm-ai-pilot` with a named human owner |
| Allowed model | Exactly the one `confirmed-live` canary ID |
| Allowed endpoint category | `chat` only; add `models` only if the deployed Twenty build proves it requires discovery |
| Expiry | Seven days after canary start |
| Concurrency | 1 |
| Request rate | 5 requests/minute and 50 requests/day |
| Budgets | US$1/day, US$5/week, and US$15/month, or lower human-approved non-null caps |
| Network | Stable Twenty server egress IP allowlist if the deployment has one |
| Revocation | Human owner and rollback operator named before creation |

The exact caps are a conservative pilot proposal, not current configuration. The existing four
all-model, no-budget keys fail this contract. Empty model and endpoint allowlists are also unsafe
because installed OmniRoute source treats them as allow-all.

Twenty-side permissions must be independent of gateway permissions. Assign the canary AI agent a
dedicated role with read access only to sanitized pilot records and only the necessary fields. No
create, update, delete, email, workflow-management, export, or cross-workspace permission is part
of the pilot.

## Error and freshness states

| State | Trigger | Required behavior |
| --- | --- | --- |
| `LICENSE_REQUIRED` | Self-hosted Organization entitlement absent or unverified | Do not configure the provider; route to a human licensing decision. |
| `UNCONFIGURED` | Provider, model entry, base URL, or server secret missing | Feature unavailable; no fallback to an unrelated provider. |
| `AUTH_REQUIRED` | OmniRoute 401 / `AUTH_002` | Stop; never retry with a management token or expose the response body to users. |
| `POLICY_DENIED` | Model or endpoint returns 403 | Treat as expected least-privilege enforcement; do not widen the key automatically. |
| `MODEL_STALE` | Exact ID returns 400/404 or disappears from the catalog | Disable the Twenty model; require a fresh catalog and human re-approval. |
| `BUDGET_EXHAUSTED` | Per-key budget or token policy rejects the request | Stop until the next approved window; never switch to an unbudgeted shared key. |
| `RATE_LIMITED` | 429 | Honor retry timing with a small bound; then fail visibly without duplicate CRM actions. |
| `POLICY_UNAVAILABLE` | Gateway policy backend returns 503 | Fail closed; do not bypass key controls. |
| `UPSTREAM_UNAVAILABLE` | Provider/gateway 5xx | Bounded retry for idempotent text generation only; no hidden model-route change. |
| `TIMEOUT` | Client deadline reached | Abort and mark the run indeterminate; do not write a partial result to CRM. |
| `MALFORMED_RESPONSE` | Missing text, invalid stream, or unusable usage fields | Reject the output and retain only redacted diagnostic metadata. |
| `CAPABILITY_MISMATCH` | Unsupported role, tool call, modality, or reasoning parameter | Disable that capability; do not silently strip semantics without review. |
| `CATALOG_STALE` | Last exact-ID check exceeds the approved freshness window or conflicts with another source | Block activation and refresh read-only evidence. |

No error path may fall back to an existing all-model key, an `auto/*` route, or a provider outside
the approved data-handling boundary.

## Test matrix

| Stage | Test | Data/cost boundary | Pass condition |
| --- | --- | --- | --- |
| 0 — static | Parse the redacted provider shape against the deployed Twenty schema; prove `npm` versus `type`, `/v1` exactly once, one model entry, and no committed secret. | Local only; no key or network. | Schema accepts the redacted shape and secret scanning finds no credential. |
| 1 — unauthenticated negative | Read `/v1/models` without a key. | BrowserOS neo, read-only, no model call. Already observed on 2026-08-10. | 401 / `AUTH_002`; no catalog disclosure. |
| 2 — authenticated catalog | With the newly approved inference key, read the model list only if `models` was explicitly granted. | Read-only; no inference. | Exact canary ID appears; forbidden IDs are not selectable by policy. |
| 3 — policy negatives | Attempt a disallowed model and a disallowed endpoint with synthetic content. | Expected gateway rejection before upstream inference. | 403/denial, zero provider usage, no key widening. |
| 4 — stub compatibility | Exercise Twenty's provider adapter against a local OpenAI-compatible stub for roles, streaming, timeouts, malformed responses, and usage fields. | Local only; no live key or CRM data. | Every error maps to the state table and no partial CRM write occurs. |
| 5 — paid canary | One human-triggered text-only summarization of sanitized synthetic data with the exact model. | One paid call only after explicit approval. | Valid output, expected model ID, usage recorded in both systems, cost within cap, no secret/PII in logs. |
| 6 — Twenty role gate | Run the canary through a read-only AI-agent role against sanitized pilot records. | No real prospect/customer data; no writes. | Agent cannot read excluded fields or perform any mutation. |
| 7 — rollback drill | Disable the Twenty provider/default, revoke the dedicated key, then repeat the canary. | No upstream call should succeed. | Feature is unavailable and the revoked key returns 401; other OmniRoute clients remain unaffected. |

Stages 2–7 are future approval-gated work. This research task performed only the Stage 1 negative
read and local/source inspection; it made no model call.

## Rollback

1. Disable the OmniRoute model in Twenty and move any Twenty default role back to its previously
   recorded value.
2. Remove or disable only the `omniroute` custom provider from the Twenty server secret/admin
   surface.
3. Revoke only `twenty-crm-ai-pilot` in OmniRoute.
4. Confirm the revoked credential fails and Twenty shows `UNCONFIGURED` rather than falling back.
5. Confirm no OmniRoute provider, routing rule, shared key, or other client changed.
6. Preserve redacted usage/error evidence for review; do not preserve the key or sensitive prompts.

Rollback does not require an OmniRoute provider or model-routing change. Record the current Twenty
defaults before activation so step 1 is deterministic.

## Exact approvals still required

| Approval | Human decision/evidence required |
| --- | --- |
| Twenty entitlement | Confirm the deployed instance is self-hosted, has an active Organization license, and exposes the custom-provider feature. |
| Deployed schema | Confirm the live Twenty version and the accepted provider shape. Current source/admin UI use `npm: "@ai-sdk/openai-compatible"`, while the same commit's `.env.example` shows `type: "openai-compatible"`; do not paste either into production until the deployed parser is proven. |
| Model | Select one exact ID from an authenticated live catalog, record capabilities/data terms/cost, and approve its Twenty composite ID. |
| Key creation | Approve a new inference-only key with exact model, `chat` endpoint, expiry, rate, daily/weekly/monthly budgets, and optional IP allowlist. Explicitly reject reuse of the four current shared keys. |
| Secret storage | Choose the Twenty server secret surface and verify at-rest handling, redaction, backup/export behavior, and operator access before inserting the key. |
| Data boundary | Approve sanitized synthetic canary data and the dedicated read-only Twenty AI-agent role. No real prospect/customer data is implied. |
| Paid call | Approve exactly one Stage 5 canary, its maximum budget, operator, observation window, and stop conditions. |
| Promotion | After the test matrix, separately approve any real data, chatbot workspace access, workflow mutation, tool use, Responses API, second model, `auto/*` route, production duration, or higher budget. |

Until every approval through the paid-call row is explicit, the correct state is **design complete,
integration inactive**.

## Source notes and unresolved contradictions

- Twenty's [AI FAQ](https://docs.twenty.com/user-guide/ai/how-tos/ai-faq) is the official license
  boundary; its developer docs describe apps but do not currently document this custom-provider
  contract end to end.
- The pinned Twenty source is used because it exposes the actual provider registry, schema, and SDK
  factory. Recheck the deployed version before implementation.
- At the pinned commit, the official
  [`.env.example`](https://github.com/twentyhq/twenty/blob/0ef79db84202e333fb6007347590294793a88d83/packages/twenty-server/.env.example#L105-L122)
  uses a `type` field, but the
  [runtime schema](https://github.com/twentyhq/twenty/blob/0ef79db84202e333fb6007347590294793a88d83/packages/twenty-server/src/engine/metadata-modules/ai/ai-models/types/ai-provider-config.schema.ts)
  requires `npm`, and the admin UI emits `@ai-sdk/openai-compatible`. This is an unresolved
  source-level contradiction, not permission to guess.
- Forwarded live OmniRoute v3.8.49 state is newer than installed local v3.8.46 source. Live control
  labels and behavior win at approval time.
- The local OMP cache count (1,699) and forwarded live endpoint count (1,157) differ on the same
  date. Catalog count and cached zero-cost metadata must not be used as availability or pricing
  claims.

## Non-actions

- No credential was created, copied, displayed, stored, or rotated.
- No Twenty provider, model, role, default, or deployment was changed.
- No OmniRoute provider, model route, key, budget, or policy was changed.
- No paid or free inference request was made.
- No real CRM, prospect, customer, or personal data was read or introduced.
- No external send, publication, merge, or access-policy change was authorized.
