---
description: "Curia docs site (apps/docs) build + Cloudflare Workers Static Assets deploy runbook."
sources:
  - curia-ai/apps/docs (relocated from public docs tree, AGE-29)
status: canonical
tags:
  - curia
  - engineering
  - operations
  - runbook
  - internal
  - canonical
title: Curia — docs site deploy runbook
---
# Curia — docs site deploy runbook

Internal operations reference for the Curia documentation site (`apps/docs`, Fumadocs on Next.js). Complements [Curia — tech stack](./curia-tech-stack.md).

> **Why this lives here:** relocated from `curia-ai/apps/docs/content/docs/operators/cloudflare-deploy.mdx` (AGE-29). That path is served on the **public, indexable** domain `docs.agenticengineering.lat` — operator/runbook material must not sit on a public surface. See [Public wiki boundary](./public-wiki-boundary.md). No secrets were exposed by the original page; this is a pattern fix.

The docs site is isolated in `apps/docs` so it does not contaminate the TanStack Start runtime of `apps/web`. It uses Fumadocs on Next.js with `output: "export"`, so the deploy artifact is fully static.

## Local build

```bash
pnpm --filter @curia/docs build
pnpm --filter @curia/docs typecheck
pnpm --filter @curia/docs lint:eslint
```

The build generates `apps/docs/out`.

## Workers Static Assets

Cloudflare recommends Workers Static Assets for new static sites. This workspace's `wrangler.jsonc` points at:

```json
{
  "name": "curia-docs",
  "assets": {
    "directory": "./out"
  }
}
```

Proposed deploy:

```bash
pnpm --filter @curia/docs build
cd apps/docs
pnpm exec wrangler deploy
```

## Domain

Before selecting a hostname, discover CLI/API-managed zones. Preference: `docs.<curia-domain>` if Curia already has its own zone; otherwise use a subdomain managed by Agentic Engineering, or a temporary `workers.dev`/`pages.dev` URL, and leave an explicit blocker. Current custom domain: `docs.agenticengineering.lat` — **treat everything under `apps/docs/content/**` as world-readable.**

## Operations checklist

- Local build succeeds.
- Docs workspace typecheck and lint pass.
- `pnpm exec biome check .` from the root with no new errors.
- Deploy URL reachable.
- Custom domain reachable if configured.
- Tracking ticket + GitHub PR updated with URL, commit, and commands.

## Documentation security

Do not include secrets in docs. Variables and bindings live in `.env.example`, Wrangler secrets, or the corresponding Cloudflare system. Do not document prompts, OCR text, RFC, CURP, R2 keys, or real client data. Because the docs site is public, content is also subject to [Public wiki boundary](./public-wiki-boundary.md).
