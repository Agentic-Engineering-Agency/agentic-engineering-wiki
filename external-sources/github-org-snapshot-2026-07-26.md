---
type: source
description: "Read-only audit record of Agentic-Engineering-Agency repositories, activity, pull requests, and selected project state."
source_url: https://github.com/Agentic-Engineering-Agency
date_fetched: 2026-07-26
preservation: text-extracted
tags: [ source, immutable, layer-ingest, text, github, operations ]
title: GitHub organization snapshot — 2026-07-26
source_type: live-github-api-audit
observed_at: 2026-07-26
---

## Capture method

Read-only GitHub CLI and API queries against the `Agentic-Engineering-Agency` organization on 2026-07-26. No edits, pushes, reviews, merges, comments, settings changes, archival, or deletion were performed.

Representative commands:

```bash
gh api 'orgs/Agentic-Engineering-Agency/repos?per_page=100&type=all' --paginate
gh pr list -R Agentic-Engineering-Agency/REPO --state open
gh pr view N -R Agentic-Engineering-Agency/REPO --json isDraft,mergeable,mergeStateStatus,statusCheckRollup,reviews
gh run list -R Agentic-Engineering-Agency/REPO
gh api repos/Agentic-Engineering-Agency/REPO/compare/main...dev
```

## Organization observations

| Observation | Recorded value |
|---|---:|
| Repositories | 75 |
| Private repositories | 50 |
| Public repositories | 25 |
| Non-archived repositories | 50 |
| Archived repositories | 25 |
| Repositories with default-branch activity in 30 days | 17 |
| Default-branch commits in 30 days | 212 |
| Repositories with default-branch activity in 7 days | 3 |
| Default-branch commits in 7 days | 15 |
| Open pull requests | 35 |
| Draft pull requests | 22 |
| Open pull requests untouched for at least 30 days | 16 |
| Open pull requests untouched for at least 60 days | 7 |
| Conflicting open pull requests | 6 |
| Failing open pull requests | 2 |
| Approved, green, mergeable, CLEAN pull requests | 7 |

Seven-day activity was recorded in `prism-arena` (8 commits), `landing-page` (6), and `agentic-engineering-gtm` (1).

## Selected repository observations

- `landing-page`: recent work added audience-specific decks, founder contact paths, TidyCal integration, proof evidence, Spanish routes, and offer-ladder changes. GitHub state alone did not prove current production parity or end-to-end conversion tracking.
- `agentic-engineering-gtm`: private repository; one 2026-07-21 bulk commit recorded 288 files and 12,923 additions, including financial models, one-pagers, pitch decks, investor material, publishing material, and Sites builds.
- `lead-weekly-skill`: private repository; its 2026-06-10 self-report recorded 50 curated leads, 80 drafts, and 50 people uploaded to Twenty. Last repository commit observed 2026-06-23; no Actions workflow was observed.
- `linkedin-prospecting-agent` pull request 33: draft, 33 commits, 100 files, 33 commits ahead of `main`, CLEAN, zero reviews; checks dated 2026-05-30.
- `curia-ai`: staging CI/deploy evidence observed green through 2026-07-16. Pull requests 711 and 716 were approved, green, and CLEAN. Pull request 708 was green and CLEAN with changes requested concerning delivered-event retry handling.
- `pricegenius`: Mercado Libre OAuth, read-only catalog sync, and onboarding were present; scheduled quality checks were green through 2026-07-23; no customer evidence was observed in the repository audit.
- `Defade`: default branch last changed 2026-05-11. A build succeeded and the subsequent deployment job failed while Wrangler was being installed through `wrangler-action`. Production parity was not established.
- `muta`: `dev` was six commits ahead of `main`; three stale draft pull requests were observed, two conflicting.
- No repository named `forgecraft` was returned by the organization query. `buildcraft` was present. This observation does not rule out another organization or a prior rename.
- `agentic-engineering-hq` was empty. `command-center` contained code with its latest default-branch commit observed on 2026-04-22.

## Workflow observations

- GitHub Copilot review automation was visible in 18 repositories, Claude or Anthropic automation in 5, and CodeQL in 3.
- The `omp-pantheon` dependency-update workflow recorded 317 tests passed, 1 skipped, and 0 failed; branch push succeeded; pull-request creation failed because workflow permissions were read-only. Thirty-five update branches were observed.

## Limits

This is a point-in-time audit record. Commit counts include bot, generated-file, boundary-date, and bulk-import activity. Repository artifacts prove implementation or documentation work, not customer demand, revenue, production parity, or conversion performance.
