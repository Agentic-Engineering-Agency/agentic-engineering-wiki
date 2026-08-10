---
type: research-note
description: >-
  Provisional package boundary, data model, permissions, private deployment path, rollback,
  and blockers for a Revenue Workcell app on the self-hosted Agentic Engineering Twenty CRM.
status: provisional
sources:
  - https://docs.twenty.com/developers/introduction
  - https://docs.twenty.com/developers/extend/apps/getting-started/quick-start
  - https://docs.twenty.com/developers/extend/apps/getting-started/concepts
  - https://docs.twenty.com/developers/extend/apps/getting-started/project-structure
  - https://docs.twenty.com/developers/extend/apps/config/application
  - https://docs.twenty.com/developers/extend/apps/config/roles
  - https://docs.twenty.com/developers/extend/apps/config/install-hooks
  - https://docs.twenty.com/developers/extend/apps/data/objects
  - https://docs.twenty.com/developers/extend/apps/data/relations
  - https://docs.twenty.com/developers/extend/apps/logic/logic-functions
  - https://docs.twenty.com/developers/extend/apps/operations/publishing
  - https://docs.twenty.com/developers/extend/apps/operations/sync-and-recovery
  - https://docs.twenty.com/developers/extend/apps/operations/testing
  - research/lovable-pro-lite-strategy-2026-08-10.md
  - external-sources/founder-dashboard-source-snapshot-2026-07-26.md
  - articles/claims-registry.md
created: 2026-08-10
author: Codex
tags: [ research, provisional, internal, twenty, crm, revenue-workcell, custom-app ]
title: Twenty Revenue Workcell custom-app boundary
---

## Question

What is the smallest safe local Twenty custom-app package for
`twenty.agenticengineering.lat`, given the current Revenue Workcell boundary and the live
instance, without changing the CRM, credentials, DNS, deployment, or records?

## Decision

Build locally, but do not install, one private **Twenty App** named
`Agentic Engineering Revenue Workcell`, package version `0.1.0`. The package is a declarative
qualification-evidence adjunct with one custom object, no autonomous behavior, and a deny-all app
runtime role.

The governed package now lives in
`Agentic-Engineering-Agency/twenty-revenue-workcell-app`. It contains exactly one headless
`Workflow Fit Check` object, a deny-all runtime role, no logic or UI entities, and a fail-closed
Twenty engine range of `>=2.29.0 <3.0.0`. The app must not replace the existing Person upsert integrations, become pipeline authority, or
connect the external Revenue Workcell to CRM writes. It must not add AI agents merely because the
live instance exposes AI settings. The first install remains blocked because the live server is
Twenty `2.26.1`, while this reviewed package targets `2.29.x`; live metadata, permissions, and
recovery evidence also remain incomplete.

## Evidence state

### Current first-party documentation

BrowserOS neo inspection on 2026-08-10 established the following from Twenty's current developer
documentation:

- The supported extension mechanism is a sandboxed TypeScript **Twenty App**. `twenty-sdk`
  declarations are analyzed into a manifest that can add objects, fields, relations, roles, logic
  functions, front components, views, page layouts, skills, and agents. This is distinct from an
  external REST/OAuth integration or a fork of Twenty core ([concepts](https://docs.twenty.com/developers/extend/apps/getting-started/concepts)).
- The current scaffold requires Node.js 24.5 or later and Yarn 4, and begins with
  `npx create-twenty-app@latest` ([quick start](https://docs.twenty.com/developers/extend/apps/getting-started/quick-start)).
- The current documented scaffold pins `twenty-sdk` and `twenty-client-sdk` together at `2.20.0`.
  It also lists `twenty-ui` `1.0.0-alpha.1` for the scaffolded UI, which this headless package does
  not need ([project structure](https://docs.twenty.com/developers/extend/apps/getting-started/project-structure)).
- An internal app can be built as a tarball and published privately to one Twenty server. A
  deployed version must increase strictly by semver. `engines.twenty` is enforced by the server
  at deploy and install time when the server has `APP_VERSION` configured
  ([publishing](https://docs.twenty.com/developers/extend/apps/operations/publishing)).
- `yarn twenty plan` previews metadata changes without applying them. Destructive changes are
  identified explicitly; `--force` bypasses their confirmation and is therefore prohibited for
  this package ([syncing and recovery](https://docs.twenty.com/developers/extend/apps/operations/sync-and-recovery)).

These are **observed documentation facts**, not evidence that the self-hosted instance runs Twenty
`2.20.0`.

### Live instance

Two read-only evidence paths were available:

1. BrowserOS neo reached `https://twenty.agenticengineering.lat/welcome`, observed the title
   `Sign in or Create an account`, the heading `Welcome, Agentic Engineering.`, an Email field, and
   `Continue`. The public `/healthz` response was HTTP 200 with `status: ok`. The public application
   bundle was `assets/index-CBMIjNZc.js`; its declared chunks include `SettingsApplications`,
   application permission UI, and logic-function settings. No server release number was exposed,
   and no sign-in action was taken.
2. The goal Coordinator supplied a dated authenticated, read-only Comet observation that
   `Settings → Applications → Developer` is enabled. The visible apps were `Standard (Seeded)`,
   `Custom (Local)`, and `Linear (NPM)`. `Settings → AI` exposed Models, Skills, Tools, and Usage;
   the visible defaults were `Smart = GPT-5.6 Luna` and `Fast = GPT-5 Mini · Best`. This note did
   not independently reproduce that authenticated observation in BrowserOS neo.

Together these observations support the **mechanism**: this server build has application and AI
surfaces. A later authenticated server inspection established version `2.26.1`. They do not establish deployment owner, package compatibility,
workspace schema, or permission configuration. No CRM record, setting, application, credential,
or model default was changed.

### Existing repository integrations

The workspace now owns the headless app package above, but still has no server/deployment
repository for the live Twenty origin. It also has three server-side Person-write paths:

| Repository evidence | Current behavior | Boundary |
| --- | --- | --- |
| `landing-page/lib/twenty-crm.ts` | `POST /rest/people?upsert=true` for contact forms | Write-only; typed failures and PII-safe error logging; no pipeline read model |
| `landing-page/lib/newsletter/twenty.ts` | Best-effort confirmed-subscriber Person mirror | Write-only; no app manifest |
| `curia-landing/worker/index.ts` | Cloudflare Worker Person upsert | Write-only; secret remains server-side; no app manifest |

The immutable [founder dashboard source snapshot](../external-sources/founder-dashboard-source-snapshot-2026-07-26.md)
already classifies Twenty as a working confirmed-contact mirror with an unverified read side. The
[Revenue Workcell strategy](./lovable-pro-lite-strategy-2026-08-10.md) explicitly permits no CRM
write in version 1. The [claims registry](../articles/claims-registry.md) also treats current
pipeline state as unverified. This app must preserve those boundaries.

## Supported package envelope

The product repository began from the official scaffold and removed the starter front component,
navigation item, page layout, publish workflow, and embedded development credential. The reviewed
package pins `twenty-sdk` and `twenty-client-sdk` to `2.29.0`; its intended contract is:

```json
{
  "name": "twenty-revenue-workcell",
  "version": "0.1.0",
  "private": true,
  "dependencies": {},
  "devDependencies": {
    "twenty-client-sdk": "2.29.0",
    "twenty-sdk": "2.29.0"
  },
  "engines": {
    "node": "^24.5.0",
    "twenty": ">=2.29.0 <3.0.0"
  }
}
```

The conservative `engines.twenty` range is implemented and fail-closed. It is not a claim about
the live server. Do not omit it to bypass compatibility. Because the live server is older, either upgrade the
server through its owned runbook or regenerate and validate the app against the actual supported
SDK; do not guess at compatibility.

Minimum source tree:

```text
twenty-agentic-engineering-revenue-workcell/
├── package.json
├── src/
│   ├── application-config.ts
│   ├── default-role.ts
│   ├── objects/workflow-fit-check.object.ts
│   ├── fields/company-workflow-fit-check.relation.ts
│   ├── fields/workflow-fit-check-company.relation.ts
│   ├── fields/person-workflow-fit-check.relation.ts
│   ├── fields/workflow-fit-check-person.relation.ts
│   └── __tests__/
│       ├── application-config.test.ts
│       └── schema.integration-test.ts
└── .github/workflows/ci.yml
```

Every entity receives a generated universal identifier exactly once when the package repository is
created. Identifiers must remain stable across syncs and releases; this research note intentionally
does not invent placeholder UUIDs.

## App boundary for Revenue Workcell

| Concern | Owner after `0.1.0` | App responsibility |
| --- | --- | --- |
| Confirmed people and companies | Existing Twenty objects and current inbound adapters | Link to existing records; do not duplicate email, phone, message, company name, or form payloads |
| Workflow Fit Check evidence | New `workflowFitCheck` object | Hold a small reviewed qualification record with evidence state and sources |
| Opportunity, stage, amount, probability, close date | Unresolved CRM authority / AE-370 | No new fields, relations, migration, or writes |
| Prospect Result Room and bilingual presentation state | Revenue Workcell | No session, tenant, or presentation state in Twenty |
| Decisions, claims, and provenance policy | Wiki/OpenKnowledge | Reference evidence; do not become the claims registry or decision log |
| Tasks and delivery state | Linear | No task mirror |
| Outreach and sends | Human commercial owner | No send action, webhook, cron, or database trigger |
| AI model selection and agent execution | Existing Twenty AI administration | No skill, agent, tool, or model dependency in `0.1.0` |

### Single-object schema

Twenty automatically adds base fields such as `id`, `name`, `createdAt`, `updatedAt`, `createdBy`,
`updatedBy`, and `deletedAt` to a custom object. The app adds only the fields below
([objects](https://docs.twenty.com/developers/extend/apps/data/objects)):

The object identity is `workflowFitCheck` / `workflowFitChecks`, labeled `Workflow Fit Check` /
`Workflow Fit Checks`, and pinned to the standard record-page experience. The base `name` field is
the human-readable check title.

| Field | Twenty type | Required behavior |
| --- | --- | --- |
| `state` | `SELECT` | Non-null; `DRAFT`, `REVIEW_READY`, or `DECIDED`; default `DRAFT` |
| `recommendation` | `SELECT` | `MORE_EVIDENCE`, `NO_FIT`, or `BLUEPRINT_REVIEW`; nullable until decided |
| `evidenceState` | `SELECT` | Non-null; `OBSERVED`, `FOUNDER_DECISION`, `INFERENCE`, or `MISSING_EVIDENCE`; default `MISSING_EVIDENCE` |
| `checkedAt` | `DATE_TIME` | Nullable until a human review completes |
| `language` | `SELECT` | Non-null; `EN` or `ES`; default `EN`; identifies source language, not a UI locale |
| `workflowSummary` | `RICH_TEXT` | Nullable bounded summary; no direct contact data or unsupported ROI claim |
| `riskFlags` | `MULTI_SELECT` | Required; defaults to `HUMAN_APPROVAL`; options also include `DATA_BOUNDARY`, `SYSTEM_AUTHORITY`, `SECURITY_PRIVACY`, and `ECONOMIC_EVIDENCE` |
| `sourceReferences` | `ARRAY` | Default empty; dated URLs or repository/wiki references; never credentials or unrestricted workspace payloads |
| `company` | nullable `RELATION` | Many checks to one standard Company; deletion uses `SET_NULL` |
| `person` | nullable `RELATION` | Many checks to one standard Person; deletion uses `SET_NULL` |

Each relation is bidirectional and therefore needs both manifest fields. Standard-object targets use
`STANDARD_OBJECT_UNIVERSAL_IDENTIFIERS`; the many-to-one side lives on `workflowFitCheck`, and the
reverse one-to-many field lives on Company or Person
([relations](https://docs.twenty.com/developers/extend/apps/data/relations)). `SET_NULL` prevents a
contact cleanup from cascading into qualification evidence.

No Opportunity relation is permitted in `0.1.0`. No field stores pricing, probability, expected
savings, automatic score, email body, transcript, prompt, or result-room access token.

### Actions

The package contains **no logic functions**. It therefore defines no HTTP route, cron trigger,
database event, background job, workflow action, AI tool, install hook, or uninstall hook. Those
are supported Twenty mechanisms, but they create authority and rollback surfaces that this first
package does not need ([logic functions](https://docs.twenty.com/developers/extend/apps/logic/logic-functions),
[install hooks](https://docs.twenty.com/developers/extend/apps/config/install-hooks)).

Allowed behavior is limited to a named internal human using standard Twenty object screens to:

- create a Workflow Fit Check record linked to an existing Company and optionally a Person;
- edit its summary, evidence state, sources, risk flags, and recommendation; and
- move it to `DECIDED` after review.

The external Revenue Workcell remains read/write-disconnected from CRM in version 1. A future
read-only adapter requires a separate API-key role, field allowlist, privacy review, and accepted
read contract; it is not implied by installing this app.

### Permissions

`application-config.ts` declares no application or server variables, secrets, install hooks, or
custom settings component. `default-role.ts` uses exactly one `defineApplicationRole()` with:

- all global read, update, soft-delete, destroy, and settings flags false;
- no object permissions;
- no field permissions;
- no system permission flags; and
- `canBeAssignedToAgents`, `canBeAssignedToUsers`, and `canBeAssignedToApiKeys` false.

That role keeps the app runtime inert. Twenty documents that app logic and front components inherit
this default role and that permissions are enforced at the API layer
([roles and permissions](https://docs.twenty.com/developers/extend/apps/config/roles)).

Human access is not auto-granted by the package. Before real use, a workspace administrator must
review an existing internal role and explicitly grant only read/update access to
`workflowFitCheck`; soft delete, destroy, settings updates, API-key assignment, agent assignment,
and external-user assignment remain denied. The package does not rely on row-level security.
External prospect access is out of scope; any future tenant-facing Twenty access must first verify
that the live plan enforces row-level predicates.

## Install and private deployment path

No step below was executed against the live instance.

1. Choose and own a dedicated product repository. No current repository owns this package; do not
   place product code in the workspace root or the wiki.
2. Scaffold with `npx create-twenty-app@latest`, record the generated universal identifiers, remove
   starter UI entities, and pin the reviewed SDK pair.
3. Run only against an ephemeral/local Twenty server first. Keep remote URLs and credentials in the
   CLI's local config or CI secrets; commit none of them.
4. Run `yarn lint`, `yarn typecheck`, `yarn test:unit`, and `yarn test`. The integration test must
   install the app, verify the object/fields/relations and deny-all runtime role, then uninstall it
   on the disposable server ([testing](https://docs.twenty.com/developers/extend/apps/operations/testing)).
5. Run `yarn twenty dev:build --tarball`, retain the manifest and tarball digest as release evidence,
   and run `yarn twenty plan` against a non-production target. The accepted plan is add-only:
   `0 to destroy`.
6. Confirm the target's actual Twenty version and `APP_VERSION`; keep
   `engines.twenty` fail-closed. Confirm that the existing `Custom (Local)` registration and its
   universal identifiers do not collide with this app.
7. Take an operator-owned database and metadata backup and prove a restore on a non-production
   instance. Turn auto-upgrade off for the first live install.
8. Add the production remote locally with `yarn twenty remote:add --url <server> --as production`,
   then have the named operator publish the reviewed tarball with
   `yarn twenty app:publish --private --remote production`.
9. In `Settings → Applications → Registrations`, verify the package digest/version and install it
   only into the intended workspace. Do not use a public npm/marketplace release.
10. Apply reviewed human role permissions manually, create sanitized demonstration records, and
    re-run the acceptance checks before any real data.

## Acceptance evidence

| Gate | Pass evidence |
| --- | --- |
| Package | Exact source commit, `0.1.0` tarball digest, generated manifest, stable universal identifiers |
| Compatibility | Actual target server version satisfies `engines.twenty`; no skipped or unknown check |
| Schema | One object, the listed fields, four relation fields, and no Opportunity mutation |
| Plan | `yarn twenty plan` shows the reviewed add-only diff and `0 to destroy` |
| Runtime authority | Default application role has no object, field, settings, system, user, API-key, or agent authority |
| Human authority | Named internal role can read/update the object and cannot delete/destroy or update settings |
| Behavior | No logic functions, routes, schedules, events, workflow actions, AI entities, UI entities, or external sends |
| Privacy | Only sanitized records; no email, phone, message body, transcript, credentials, or cross-prospect data duplicated |
| Recovery | Database/metadata restore drill passes on non-production; uninstall behavior is captured |
| Existing flows | Landing Page, newsletter, and Curia Person upserts continue unchanged in integration tests |

## Rollback

Twenty's release path requires increasing versions and rejects a downgrade. Rollback therefore
means **stop, preserve evidence, and roll forward**, not installing an older package over a newer
one.

1. Before real data, if installation or permissions are wrong, stop use and uninstall with
   `yarn twenty app:uninstall` only after confirming the disposable or sanitized scope. Treat
   uninstall as destructive to app-owned metadata/data until the local integration test proves its
   exact behavior.
2. For a code or manifest defect after `0.1.0`, revert the source change in Git, bump to `0.1.1`,
   run the complete gates again, and deploy the higher corrective version.
3. For any migration that would destroy metadata or data, stop before apply. Export affected
   records, take a database/metadata backup, and add a separately reviewed pre-install backup or
   validation hook. A failing synchronous post-install hook does not roll schema changes back.
4. If live records may be affected, do not uninstall or reset. Isolate the app, retain the failed
   manifest/plan/log evidence without personal data, and restore through the self-hosted
   infrastructure owner's tested database procedure.
5. `yarn twenty docker:reset` is local-only and a last resort; it deletes all local data and is
   prohibited against the live instance.

## Exact blockers

| Blocker | Why it blocks installation | Evidence that closes it |
| --- | --- | --- |
| Live Twenty `2.26.1` is below the package engine range | SDK `2.29.0` and `engines.twenty >=2.29.0` deliberately fail closed | Owned Twenty upgrade to a compatible release, or a separately regenerated and fully validated 2.26-compatible package |
| Live metadata was not inventoried | Existing `Custom (Local)`, Linear, Person, Company, and custom field identifiers may collide or change the plan | Authenticated read-only export of installed app manifests and relevant object/field metadata |
| CRM authority remains unresolved for pipeline data | Adding Opportunity fields or relations could silently pre-empt AE-370 | Accepted CRM authority decision; `0.1.0` proceeds only without Opportunity mutation |
| Production operator and permission role are unnamed | Install and human access would be unaudited | Named operator plus reviewed role diff showing read/update only |
| Backup and restore are unproved | App uninstall or later schema migration may remove app-owned data | Successful non-production database/metadata restore drill with owner and timestamp |
| Existing inbound integrations lack a joint regression gate | A schema change could break Landing Page, newsletter, or Curia upserts | Integration run proving all three Person upsert contracts remain unchanged |
| External read contract is absent | A Revenue Workcell API key could expose direct CRM or cross-prospect data | Separate approved read-only field allowlist, API-key role, privacy review, and tenant isolation test |
| AI scope has no accepted need or cost/permission contract | Live model defaults do not authorize autonomous CRM actions | Separate spec and approval; AI entities remain absent from `0.1.0` |

## Recommendation

Keep this as the implementation boundary until the blockers close. The smallest safe deliverable
today is the reviewed source package and tarball, not a live installation. Local lint, typecheck,
unit tests, manifest validation, tarball build, and credential scan passed; the default runtime
role is deny-all. CI run
[`31391168566`](https://github.com/Agentic-Engineering-Agency/twenty-revenue-workcell-app/actions/runs/31391168566)
also installed and synchronized the package against a disposable Twenty `2.29.0` instance,
verified the live object, fields, relations, and deny-all role, and required a successful
uninstall. The `0.1.0` tarball SHA-256 is
`cee7defb8e29741035e123d6e676f9e4f52f2d9643ef3281c7161afa414c8dfd`.
Live-version compatibility, production metadata, joint inbound regression, and backup/rollback
evidence remain release gates. Do not weaken `engines.twenty` merely to install on `2.26.1`.
