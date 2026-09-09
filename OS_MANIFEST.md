# Evan AI OS Manifest

> **Purpose:** this is the authority map for ChatGPT, Codex, Claude Code, and humans. Read this file before using or modifying any asset in this repository.

## 1. Status model

`canonical`, `frozen`, `active`, `draft`, and `archived` are not all the same kind of property. To avoid ambiguity, the OS uses two axes:

- **Authority**
  - `CANONICAL` — source of truth for the named capability/specification.
  - `SUPPORTING` — useful context, but may not override a canonical artifact.
- **Lifecycle**
  - `FROZEN` — immutable baseline. Never edit in place. A behavioral change requires a new version/file.
  - `ACTIVE` — current operational artifact. May evolve through version control.
  - `DRAFT` — exploratory; must not be treated as production truth.
  - `ARCHIVED` — retained for provenance/history; do not use for current execution unless explicitly requested.

In shorthand, an asset can therefore be both **CANONICAL + FROZEN** or **CANONICAL + ACTIVE**.

## 2. Conflict precedence

When two artifacts disagree, use this order:

```text
Explicit user instruction for the current task
>
CANONICAL + FROZEN asset applicable to that task
>
CANONICAL + ACTIVE asset
>
ACTIVE workflow / project state
>
SUPPORTING knowledge
>
DRAFT
>
ARCHIVED
```

A downstream execution layer may consume an upstream frozen methodology, but it may not reinterpret or rewrite that methodology to justify an existing position or implementation.

## 3. Canonical asset registry

| Asset ID | Path / Source | Kind | Authority | Lifecycle | Version / Pin | Mutation policy |
|---|---|---|---|---|---|---|
| `industry-analysis-v5` | Upstream: `longgold888evan/industry-research-os/skills/industry_analysis_skill_v5.md` | research / underwriting skill | CANONICAL | FROZEN | v5.0, 2026-09-08; SHA-256 `8f7d010183b8238fb6d0d21c2cf402a54c3ca7c2b4dfe464c41d25bde4be09f6`; upstream blob `1a97dde5fc4db0115700e745d1e7f271b5bde43e` | Never edit in place. Create v6+ only after explicit methodology upgrade decision. |
| `industry-discovery-layer1` | Upstream: `longgold888evan/industry-research-os/skills/layer1_v1_2_frozen_execution_rev1.md` | discovery / winner-recall skill | CANONICAL | FROZEN | v1.2 FROZEN, Execution Rev.1; upstream blob `31d575810159d0a401d0bd34a8c92a2111e559b7` | Never edit in place. Execution hardening that changes no alpha methodology must be labeled execution revision; methodology change requires new version. |
| `industry-discovery-layer1-baseline` | Historical source: `industry_evolution_winner_recall_skill_v1_2_frozen_2026-09-08.md` | frozen methodology baseline | CANONICAL | FROZEN | 2026-09-08; SHA-256 `fd27798fa6b08b4f10ed4704127622c62d4b71aeb870e8825909a4d6f5714d3c` | Preserve for provenance; operational use should prefer Execution Rev.1 because it explicitly states no alpha-methodology change. |
| `industry-execution-v1` | `skills/investment-execution/industry_analysis_execution_skill_v1.md` | capital allocation / execution skill | CANONICAL | ACTIVE | v1.0, 2026-09-08; SHA-256 source `25c53e9bb7d7812f6cd5f21c7a02fa81f36b635b45cc317c9d3609f6873a1f42`; requires frozen v5 SHA above | May be upgraded independently. Never modify v5 merely to fit execution outcomes. |
| `industry-research-pipeline` | `workflows/industry_research_os.md` | orchestration workflow | CANONICAL | ACTIVE | OS v1 | May evolve without changing frozen Layer1/v5 semantics. |
| `industry-research-upstream-code` | `longgold888evan/industry-research-os` pinned reference below | implementation repo | CANONICAL | ACTIVE | observed upstream commit `0c054e8af229398edfbba879bfb5e878ccc795d2` | Mutable implementation. Do not duplicate-edit active code in both repos. |
| `industry-research-week0` | `projects/industry-research-os/state/week0_2026-09-08.json` | state snapshot | SUPPORTING | ARCHIVED | Week 0 / 2026-09-08 | Immutable historical snapshot. New runs create new state/snapshots. |
| `career-strategy` | `knowledge/career/career_strategy.md` | durable knowledge | SUPPORTING | ACTIVE | living | Update when career plan changes. |
| `investment-philosophy` | `knowledge/investing/investment_philosophy.md` | durable knowledge | SUPPORTING | ACTIVE | living | May evolve through explicit decisions. |
| `audience-targeting-project` | `projects/audience-targeting/README.md` | project context | SUPPORTING | ACTIVE | current | Project-specific; does not override canonical AI/investment skills. |

## 4. Industry Research OS dependency graph

```text
WORLD / COMPANY EVENTS
        ↓
Layer1 v1.2 FROZEN — Discovery & Winner Recall
        ↓
Company Recall / Candidate Ledger
        ↓
V5 Quick Triage — orchestration only
        ↓
V5 Full Deep Research — frozen v5 constitution
        ↓
HC / NOT_HC / WATCH + P1–P4 + Expectation Gap + 3× Burden
        ↓
Research State Registry
        ↓
Industry Analysis Execution Skill v1
        ↓
WATCH → INITIATE → VALIDATE → PYRAMID → HOLD → HARVEST → EXIT
        ↓
Weekly Decision Loop / next evidence triggers
```

**Boundary rule:** Quick Triage, automation, persistence, code, and scheduling may evolve. Layer1 v1.2 and Industry Analysis v5 must not silently change with them.

## 5. Upstream project pin

Operational source repo:

```text
https://github.com/longgold888evan/industry-research-os
```

Observed baseline commit during OS migration:

```text
0c054e8af229398edfbba879bfb5e878ccc795d2
```

Important upstream artifacts at that pin:

```text
skills/industry_analysis_skill_v5.md
skills/layer1_v1_2_frozen_execution_rev1.md
config/research_os.yaml
docs/sec_event_first_engineering_spec_v1.md
docs/two_pass_v5_pipeline.md
scripts/sec_event_first_ingest.py
scripts/semantic_event_extract.py
state/week0_2026-09-08.json
```

The **implementation repo is the source of truth for mutable runtime code**. `evan-ai-os` is the source of truth for the cross-project authority map, durable knowledge, frozen methodology identity, execution constitution, decisions, and reusable workflows.

## 6. Agent rules

Before acting, an AI agent must:

1. Read `OS_MANIFEST.md`.
2. Identify the relevant canonical asset(s).
3. Check lifecycle before editing.
4. Never rewrite a `FROZEN` asset in place.
5. Treat `DRAFT` as hypothesis, not instruction, when it conflicts with canonical assets.
6. Preserve Point-in-Time / provenance requirements of the research skills.
7. For Industry Research OS implementation changes, modify `industry-research-os`; update this manifest/link only when authority/version/status changes.
8. Record important irreversible or framework-level choices in `knowledge/decisions/`.

## 7. Promotion rules

### DRAFT → ACTIVE
Requires a clear use case, owner, input/output contract, and at least one successful real use or eval.

### ACTIVE → CANONICAL
Requires an explicit decision that this artifact is the source of truth for a named capability.

### CANONICAL + ACTIVE → FROZEN
Requires an explicit freeze decision, immutable version identifier, and ideally a content hash.

### Any → ARCHIVED
Keep provenance and replacement pointer. Do not silently delete intellectual history.

## 8. Current migration notes

- The exact frozen v5 content supplied on 2026-09-10 has SHA-256 `8f7d010183b8238fb6d0d21c2cf402a54c3ca7c2b4dfe464c41d25bde4be09f6`; this matches the dependency hash declared by the execution skill.
- The same canonical v5 exists in the operational `industry-research-os` repo, so this OS pins that upstream artifact rather than creating a second mutable source of truth.
- The canonical Investment Execution Skill v1 is stored directly in this repo because it is a reusable cross-project operating constitution rather than implementation code.
- Week-0 state is mirrored here only as an immutable reference snapshot; live registry updates belong to the operational project until explicitly promoted.
