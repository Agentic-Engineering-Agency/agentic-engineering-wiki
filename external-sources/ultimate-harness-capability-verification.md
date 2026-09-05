---
type: source
description: "Preserved reproducible verification report at exact HEAD d4e7753."
source_url:
date_fetched: 2026-09-05
preservation: verbatim-local-text
tags: [ source, immutable, layer-ingest, internal, verification ]
title: Ultimate Harness capability verification — 2026-09-05
confidentiality: internal
source_origin: Local verification artifact supplied by the coordinating task
---

<!-- markdownlint-disable MD025 -->

# Ultimate Harness capability verification

- Date: 2026-09-05
- Repository: `/Users/eduardojaviergarcialopez/workspace/ultimate-harness`
- Exact HEAD: `d4e7753bb4dc115fb4c526499e9bf49ef3cdb70b`
- Mode: read-only capability verification; no source, configuration, dependency, provider, model, tracker, or deployment changes

## Result

Current Ultimate Harness proves that promotion has a matching passed verification artifact, but it does not authenticate `approvedBy`, bind approval or verification to the reviewed candidate/revision, or enforce declared `review_gates`. Recovery and cancellation are useful but local and best-effort; run isolation is not request deduplication.

## Fresh test evidence

The following focused command was executed fresh in this review at the exact HEAD above:

```bash
node_modules/.bin/vitest run \
  tests/promote.test.ts \
  tests/verify.test.ts \
  tests/mission-cancel.test.ts \
  tests/per-run-artifact-dirs.test.ts \
  tests/prune-old-runs.test.ts \
  tests/validate-drift.test.ts
```

Result: **6 test files passed; 82 tests passed; 0 failed**.

The repository-wide `bun run test` baseline was also executed fresh in this review, not copied from historical results. Result: **877 passed; 2 failed**. Both failures are pre-existing missing-fixture errors from `tests/spec-templates.test.ts`:

- `docs/specs/templates/feature.spec.md`
- `docs/specs/templates/epic.spec.md`

`bun run typecheck` passed. The missing fixtures are the only observed suite blocker relevant to this report.

## Reproduced negative promotion probe

The probe was executed in an ephemeral temporary harness project and left no persistent script. The following is the reproducible minimal setup:

1. Create a temporary directory and run `initializeHarness(root)`.
2. Write `.harness/missions/probe/mission.yaml` with `schema_version: uh.mission.v0`, `id: probe`, one executable required check, and `review_gates: [security-independent-review]`.
3. Write `.harness/missions/probe/diff.patch` with candidate A.
4. Write `.harness/missions/probe/verification.yaml` with `schema_version: uh.verification-result.v0`, `mission_id: probe`, `status: passed`, and one passed check.
5. Replace `diff.patch` with candidate B after the verification artifact exists.
6. Call:

```ts
await promoteMission(root, "probe", {
  approvedBy: "unauthenticated-label",
  decision: "promoted",
  changes: ["src/changed.ts"],
});
```

Observed outcome:

```json
{
  "succeeded": true,
  "decision": "promoted",
  "approved_by": "unauthenticated-label",
  "changes": ["src/changed.ts"],
  "review_gate_receipt_present": false,
  "diff_digest_present": false,
  "verification_digest_present": false
}
```

This reproduces three behaviors: `approvedBy` is a label rather than authenticated identity; a changed post-verification candidate remains promotable; and a declared review gate is not required for promotion.

## Source evidence

### Promotion identity and candidate binding

- `src/harness/promote.ts:24-30` requires only a non-empty `approvedBy` string.
- `src/harness/promote.ts:65-72` checks mission identity and requires passed verification for `promoted`.
- `src/harness/promote.ts:74-103` writes `approved_by`, optional `changes`, and an audit event without authenticating the actor or binding a digest.
- `src/harness/promote.ts:123-141` validates verification schema, matching `mission_id`, and `status: passed`; it checks no candidate digest, repository revision, review receipt, or freshness.
- `src/schema/artifacts.ts:89-108` contains no authentication, candidate/revision digest, or review-receipt field in the verification and promotion schemas.
- `src/harness/verify.ts:299-330` permits `auto-on-verify` promotion with the literal provenance label `auto-on-verify`.

### `review_gates`

- `src/schema/mission.ts:138-147` declares and defaults `review_gates` as an array of strings.
- `src/harness/verify.ts:99-193` executes required-check and acceptance-criterion commands.
- `src/harness/verify.ts:259-280` computes the result from those checks and writes no normal approval receipt.
- No verification or promotion implementation consumes `review_gates`; repository search finds persistence, fixtures, and Delivery Observatory projection only.

Conclusion: `review_gates` are declarative metadata in the inspected implementation, not executable or promotion-blocking gates.

### Recovery, cancellation, and deduplication

- `apps/hermes-plugin/dashboard/plugin_api.py:222-230` documents `_active_runs` as in-memory state lost on server restart.
- `apps/hermes-plugin/dashboard/plugin_api.py:1018-1029` treats `replay_of` as lineage metadata and executes a fresh run.
- `apps/hermes-plugin/dashboard/plugin_api.py:1083-1150` creates a new random run ID, accepts per-run isolation, starts a child, and attaches a timeout watchdog.
- `apps/hermes-plugin/dashboard/plugin_api.py:1266-1318` performs best-effort process termination; a nonterminal disk run missing from `_active_runs` returns 404 after restart, while a terminal run returns 409.
- `apps/hermes-plugin/dashboard/tests/test_plugin_api.py:615-627` explicitly accepts two concurrent runs for one mission with distinct run IDs.
- `src/harness/run-id.ts:30-34` generates random run IDs.
- `src/harness/run-id.ts:78-124` atomically replaces the index file but leaves the multi-writer read/modify/write window unlocked and last-writer-wins.
- `tests/per-run-artifact-dirs.test.ts:140-166` tests write-file atomicity only and explicitly accepts an index containing at least one of twenty concurrent entries.

Conclusion: UH provides per-run isolation, append artifacts, timeout handling, drift repair, and several idempotent cleanup operations. It does not provide request idempotency-key or payload-digest deduplication, durable post-restart process cancellation, or guaranteed multi-writer index preservation.

## Static inference kept separate

The following was not reproduced by the probe or focused tests. In `src/adapters/hermes.ts:580-623`, the `finally` block mirrors the runtime result, but terminal `latest.json` and index writes occur after the `finally`. A runner, diff-collector, or collection exception may therefore bypass those terminal writes and leave a run indexed as `running`. Treat this as a static control-flow inference requiring a dedicated fault-injection test, not as observed runtime behavior.

## State preservation

After inspection and tests:

- branch remained `main` at the exact HEAD above, two commits ahead of `origin/main`;
- no branch or worktree was created or switched;
- no tracked or staged file changed;
- pre-existing untracked `.DS_Store` and `.scratch/` remained untouched;
- no source files or tests were added for this report.
