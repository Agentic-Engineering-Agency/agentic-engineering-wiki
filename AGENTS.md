# agentic-engineering-wiki Agent Rules

Internal, source-backed operating knowledge for Agentic Engineering, Curia, the portfolio, and go-to-market work.

Workspace standards apply here: [../docs/standards/README.md](../docs/standards/README.md).
This file adds only what is specific to this repo. Where they conflict, this file wins, and the
conflict is recorded under `## Deviations`.

## Stack

- Content: Markdown with YAML front matter and wiki-style links.
- Corpus areas: canonical articles, provisional research, immutable external-source snapshots,
  and a generated codebase-wiki tree.
- Runtime and package manager: none.

## Non-negotiables

- This corpus is internal-first. Apply `articles/public-wiki-boundary.md` before reusing any
  material in customer, investor, partner, or public surfaces.
- `articles/claims-registry.md` governs external claims. Do not publish unverified, prohibited,
  stale, or audience-inappropriate claims, and do not let agents approve their own claims.
- Carry citations and evidence state with factual claims. Clearly distinguish observation,
  founder decision, plan, inference, and missing evidence.
- Preserve provenance: generated or synthesized pages may reference primary research and external
  snapshots, but must never overwrite or silently rewrite those sources.
- Put canonical operating knowledge in `articles/`, provisional synthesis in `research/`, source
  snapshots in `external-sources/`, and generated codebase documentation in `wiki/`.
- Preserve confidentiality labels and do not expose credentials, private financial terms,
  customer data, personal data, or sensitive operational paths.

## Commands

This repository defines no install, build, test, lint, or release commands.

## Verification gates

- Required for every change: confirm front matter, internal links, source citations, claim state,
  confidentiality boundary, and placement in the correct corpus area.
- Any material intended for external use requires the reviewers named in
  `articles/public-wiki-boundary.md`; editing the wiki is not publication approval.
- Generated wiki updates must be reviewed against their cited sources before they become canonical.

## Read order

1. `articles/home.md` — canonical hub and corpus boundaries.
2. `articles/claims-registry.md` — claim states, wording, evidence, and audience controls.
3. `articles/public-wiki-boundary.md` — publication and confidentiality boundary.
4. `articles/priority-rules.md` — current operating priority and escalation rules.
5. `wiki/OVERVIEW.md` — generated codebase-wiki scope and navigation.

## Scope discipline

- Update the canonical home for a fact; link from other pages instead of duplicating it.
- Keep historical or superseded evidence for provenance rather than rewriting it as current.
- Wiki edits do not authorize external sends, deployments, access changes, merges, archival, or
  deletion.

## Command Code (alternate harness)

Command Code is an **alternate** executor available in this repo, admitted for a named
capability gap (taste learning, checkpoints/rewind, plan-mode review, headless `cmd -p` runs,
native MCP with per-server permission gating). It reads this `AGENTS.md` as its memory file, so
this file remains the single instruction source. It is **not** the default — OMP is. The
generated `.commandcode/settings.json` mirrors the OMP discipline in Command Code's permission
rules and is materialized from `scripts/harness-matrix.json`; never hand-edit it. See
`docs/standards/harness.md` (Command Code section) and `docs/research/command-code-evaluation.md`.

## Deviations

- Knowledge is organized under `articles/`, `research/`, `external-sources/`, and `wiki/` rather
  than the standard `docs/` tree because those directories encode canonicality and provenance
  boundaries that are part of this corpus's evidence model.
