# AI Agent Instructions

This repository is a long-lived personal AI operating system, not a disposable project folder.

## Mandatory startup sequence

Before modifying anything:

1. Read `OS_MANIFEST.md`.
2. Read the relevant local `README.md` / `CANONICAL.md`.
3. Determine the asset's Authority and Lifecycle.
4. Identify the source-of-truth repository if the asset is linked upstream.
5. If promoting information from conversation/project work, read `workflows/memory_knowledge_promotion.md` and `evals/knowledge_promotion_eval.md`.

## Never do these

- Never edit a `FROZEN` artifact in place.
- Never let a draft note override a canonical skill.
- Never rewrite research methodology to fit a current holding or desired conclusion.
- Never duplicate-edit mutable implementation code in both `evan-ai-os` and an upstream project repo.
- Never replace a Point-in-Time historical state with current knowledge.
- Never silently delete old decisions or frozen versions.
- Never treat a long conversation as automatically durable knowledge.
- Never promote uncertain inference as fact.
- Never store passwords, access tokens, API keys, private keys, security answers, one-time codes, or other raw authentication material here.

## Where changes belong

```text
Durable knowledge / worldview / principles
→ evan-ai-os/knowledge

Important durable choice
→ evan-ai-os/knowledge/decisions

Reusable skill / workflow / agent contract
→ evan-ai-os/skills | workflows | agents

Mutable project implementation
→ the project's operational repo

Unclassified / uncertain candidate
→ evan-ai-os/inbox
```

## Conversation → durable knowledge

Use the canonical flow:

```text
conversation / file / project
→ candidate
→ classify
→ DRAFT
→ validation gate
→ ACTIVE
```

Only promote when future reuse value is high enough to justify persistent context.

Before promotion, check:

```text
durability
provenance
fact vs preference vs inference labeling
conflict with existing authority
sensitivity
correct destination
duplicate / supersession semantics
```

When an important choice will shape future behavior, create or update a Decision Record.

When a method appears reusable, do **not** immediately call it a Skill. Prefer:

```text
METHOD
→ repeated successful use
→ generalized contract
→ eval cases
→ DRAFT Skill / Workflow
→ ACTIVE
→ explicit CANONICAL decision
→ optional FROZEN baseline
```

Use `templates/knowledge_candidate.md`, `templates/decision_record.md`, and `templates/skill_promotion_record.md` where appropriate.

`registry/knowledge_registry.yaml` is a navigation index. It never overrides `OS_MANIFEST.md` or the underlying artifact.

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

Material changes to the Memory / Knowledge Promotion system should also create or supersede the relevant Decision Record under `knowledge/decisions/`.
