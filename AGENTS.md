# AI Agent Instructions

This repository is a long-lived personal AI operating system, not a disposable project folder.

## Mandatory startup sequence

Before modifying anything:

1. Read `OS_MANIFEST.md`.
2. Read the relevant local `README.md` / `CANONICAL.md`.
3. Determine the asset's Authority and Lifecycle.
4. Identify the source-of-truth repository if the asset is linked upstream.

## Never do these

- Never edit a `FROZEN` artifact in place.
- Never let a draft note override a canonical skill.
- Never rewrite research methodology to fit a current holding or desired conclusion.
- Never duplicate-edit mutable implementation code in both `evan-ai-os` and an upstream project repo.
- Never replace a Point-in-Time historical state with current knowledge.
- Never silently delete old decisions or frozen versions.

## Where changes belong

```text
Durable knowledge / worldview / decisions
→ evan-ai-os/knowledge

Reusable skill / workflow / agent contract
→ evan-ai-os/skills | workflows | agents

Mutable project implementation
→ the project's operational repo

Unclassified idea
→ evan-ai-os/inbox
```

## Industry Research special rule

For industry investing work:

```text
Layer1 v1.2 FROZEN
→ discovery / recall

Industry Analysis v5 FROZEN
→ research / underwriting

Industry Analysis Execution Skill v1
→ position actions
```

Do not merge those responsibilities.

The current implementation upstream is `longgold888evan/industry-research-os`. Consult `OS_MANIFEST.md` for pinned artifact identities and status.

## Changes to governance

Any change to a canonical/frozen designation, source-of-truth location, or dependency must update `OS_MANIFEST.md` in the same change set.
