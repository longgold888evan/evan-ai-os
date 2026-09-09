# Research State Registry

**Authority:** canonical logical model  
**Lifecycle:** active  
**Runtime source of truth:** `longgold888evan/industry-research-os/state/`

This directory keeps durable/snapshot references so the AI OS can reconstruct what the research system believed at a given point in time.

## Logical registries

```text
Industry Radar
Candidate Ledger
Research State
HC Registry
Execution State
Historical Snapshots
```

## Minimum identity fields

Every record should be identifiable by both object and time:

```yaml
entity_id:
entity_type:
research_cutoff:
first_discovered:
last_updated:
methodology_version:
source_artifacts:
```

## State-transition fields

```yaml
previous_state:
current_state:
transition_reason:
evidence_added:
evidence_lost:
counter_evidence:
next_trigger:
kill_criteria:
```

## Industry state

Track at least:

```yaml
industry:
structural_change:
stage:
direction:
stage_confidence:
bottlenecks:
new_evidence:
counter_evidence:
```

## Candidate / V5 state

Track at least:

```yaml
company:
ticker:
specific_s_curve:
s_curve_archetype:
research_priority:
v5_status:
p1:
p2:
p3:
p4:
expectation_gap:
three_x_burden:
critical_vetoes:
tail_risk:
strongest_counter_thesis:
```

## Execution state

Track at least:

```yaml
position_state:
target_position_pct_of_max_budget:
last_action:
next_add_trigger:
next_harvest_trigger:
hard_exit_criteria:
```

## Append-only principle

Historical snapshots are immutable. A later run creates a new snapshot or state transition rather than rewriting the old one.

`week0_2026-09-08.json` is the migrated baseline snapshot and explicitly records that the SEC feed was not yet audited complete. It must not be retrospectively 'cleaned up' using later evidence.
