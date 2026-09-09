---
id: DECISION-20260910-KNOWLEDGE-PROMOTION
date: 2026-09-10
domain: ai-os-governance
authority: SUPPORTING
lifecycle: ACTIVE
status: ACCEPTED
related_assets:
  - workflows/memory_knowledge_promotion.md
  - evals/knowledge_promotion_eval.md
  - registry/knowledge_registry.yaml
---

# Decision Record — Knowledge Promotion Governance

## Context

`evan-ai-os` had already separated canonical/frozen/active/draft/archived assets, but it still lacked a disciplined mechanism for deciding which insights from conversations, project work, files and experiments should become durable OS knowledge.

Without a promotion workflow, the repository risks two opposite failure modes:

1. valuable conclusions remain trapped in chat history and are hard to recover;
2. too much transient or speculative material is copied into the repository and pollutes future agent context.

## Decision

Adopt a selective Memory / Knowledge Promotion Workflow:

```text
conversation / inbox / file / project
→ candidate knowledge
→ classified draft
→ validation gate
→ ACTIVE durable knowledge
→ important decision record
→ repeated method + eval
→ CANONICAL Skill / Workflow
→ optional explicit FROZEN baseline
```

`VALIDATED` is a promotion gate rather than a new global lifecycle status. The existing lifecycle model remains `FROZEN / ACTIVE / DRAFT / ARCHIVED`.

## Why

- preserves the simplicity of the existing OS Manifest lifecycle model;
- creates an explicit bridge from conversation to versioned knowledge;
- prevents one-off ideas from becoming canonical methods;
- makes provenance, conflicts and sensitivity part of promotion;
- separates durable knowledge from ChatGPT's conversational memory;
- gives ChatGPT, Codex and Claude Code the same promotion semantics.

## Alternatives considered

### Store every useful conversation summary

Rejected because repository size and context noise would grow faster than durable value.

### Treat ChatGPT Memory as the durable knowledge layer

Rejected because memory is not an explicit, inspectable, version-controlled source of truth.

### Add `VALIDATED` as a fifth lifecycle status

Rejected. Validation is better modeled as a gate between DRAFT and ACTIVE; authority/lifecycle remain easier for agents to reason about.

### Immediately promote good methods to Skills

Rejected because one successful example is insufficient evidence of generality.

## Trade-offs / consequences

- promotion requires more discipline than simple note capture;
- some useful information will intentionally remain transient;
- registry metadata must be maintained when durable knowledge is promoted;
- important method promotions require eval cases and repeated use.

## What would change this decision

Revisit if repeated independent cases show that the workflow systematically loses high-value knowledge, creates too much maintenance overhead, or still promotes too much noisy/stale context.

## Related assets / source of truth

- Canonical workflow: `workflows/memory_knowledge_promotion.md`
- Canonical eval: `evals/knowledge_promotion_eval.md`
- Governance authority: `OS_MANIFEST.md`
- Machine-readable navigation: `registry/knowledge_registry.yaml`

## Provenance

- Decision date: 2026-09-10
- Origin: design discussion while upgrading `evan-ai-os` from a first-version knowledge base into a long-lived personal AI OS.
