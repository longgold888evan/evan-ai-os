# Evan AI OS

A personal, versioned AI operating system for durable knowledge, canonical skills, workflows, agents, prompts, evals, decisions, and project context.

## Start here

For humans and AI agents:

1. **`OS_MANIFEST.md`** — authority/status/source-of-truth map.
2. **`AGENTS.md`** — rules for ChatGPT, Codex, Claude Code, and other coding/research agents.
3. **`INDEX.md`** — navigation across the OS.

Do not treat every Markdown file as equally authoritative. `OS_MANIFEST.md` distinguishes canonical/frozen/active/draft/archived assets.

## Structure

- `knowledge/` — durable knowledge, mental models, and decision records
- `skills/` — reusable capabilities and constitutions
- `workflows/` — multi-step operating procedures and orchestration
- `agents/` — agent roles and contracts
- `prompts/` — reusable prompt assets
- `evals/` — evaluation standards
- `templates/` — repeatable artifact templates
- `projects/` — durable project context and upstream links/snapshots
- `inbox/` — unclassified capture before promotion

## The three-layer model

```text
ChatGPT Memory
→ personal context / preferences / continuity

Evan AI OS
→ explicit durable knowledge / canonical methods / decisions / governance

Operational project repos
→ mutable implementation / runtime state / production code
```

This separation prevents conversational memory from becoming a hidden source of truth and prevents the personal OS from duplicating mutable project code.

## Industry Research OS

The industry-investing stack is explicitly separated into:

```text
Layer1 v1.2 FROZEN
Discovery / Winner Recall
        ↓
Industry Analysis v5 FROZEN
Research / Underwriting
        ↓
Industry Analysis Execution Skill v1
Capital Allocation / Execution
```

The mutable implementation lives in `longgold888evan/industry-research-os`; exact authority/version pins are maintained in `OS_MANIFEST.md`.

## Core operating rule

**Frozen intellectual assets are never silently edited.** If behavior changes, create a new version and update the Manifest. Active implementation may evolve without contaminating frozen methodology.
