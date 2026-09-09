# Decision Record — Industry Research OS Governance

## Date
2026-09-10

## Decision
Separate frozen intellectual assets, cross-project execution constitutions, and mutable runtime implementation instead of treating one repository as an undifferentiated source of truth.

## Structure

```text
Evan AI OS
→ authority map
→ durable knowledge
→ reusable execution constitution
→ decisions / workflows

industry-research-os
→ operational research implementation
→ ingestion / orchestration code
→ live state
→ exact frozen industry-research artifacts already used by runtime
```

## Frozen assets

- Layer1 Industry Evolution Discovery & Winner Recall v1.2
- Industry Analysis Skill v5

They are immutable baselines. A new historical/live miss does not justify editing them unless repeated independent cases expose the same systemic failure mode.

## Active reusable execution asset

`industry_analysis_execution_skill_v1` is versioned independently from v5. Execution mistakes should normally upgrade the execution skill, not contaminate the research constitution.

## Why

1. Prevent silent methodology drift.
2. Prevent two repositories from independently editing the same mutable code.
3. Let ChatGPT/Codex/Claude Code identify authority before acting.
4. Preserve historical provenance and Point-in-Time integrity.
5. Allow orchestration/automation to evolve faster than frozen alpha methodology.

## What would change this decision

A deliberate source-of-truth migration may move an exact canonical frozen asset into `evan-ai-os`, but only if the Manifest is updated and hash identity/provenance are preserved.
