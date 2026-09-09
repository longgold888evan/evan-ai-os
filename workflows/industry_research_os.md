# Industry Research OS — Canonical Orchestration Workflow

**Status:** CANONICAL + ACTIVE  
**Methodology dependencies:** Layer1 v1.2 FROZEN + Industry Analysis v5 FROZEN  
**Execution dependency:** Industry Analysis Execution Skill v1

## Mission

Orchestrate the frozen research assets into a persistent operating loop without modifying their methodology.

```text
World Changes
↓
Layer1 Industry Evolution Discovery
↓
Company Recall
↓
V5 Quick Triage
↓
V5 Full Deep Research
↓
HC Classification
↓
Research State Registry
↓
Execution Skill
↓
Weekly Decision Loop
```

## Boundary rules

1. Layer1 optimizes **recall** and research priority, not investment attractiveness.
2. Quick Triage is an orchestration/resource-allocation stage. It cannot generate HC.
3. Only Full V5 may generate an HC conclusion.
4. The execution skill consumes V5 outputs; it does not alter V5 conclusions.
5. Persistent state records what the system believed and when. Never overwrite historical snapshots.
6. A workflow improvement does not justify changing a frozen methodology file.

## Stage 1 — World / Event Discovery

Run the operational Layer1 implementation in `longgold888evan/industry-research-os`.

Primary discovery routes:

```text
Change → Industry → Value Chain → Company
+
Event → Company → Structural Regime Change
```

Output must preserve evidence and counter-evidence.

## Stage 2 — Company Recall

Union the independent recall channels before pruning.

Typical interface:

```yaml
company:
ticker:
industry:
industry_stage:
structural_change:
value_chain_node:
why_recalled:
recall_channels:
new_weekly_evidence:
bottleneck_value_capture_hypothesis:
financial_confirmation:
counter_evidence:
cross_channel_confirmation:
```

## Stage 3 — V5 Quick Triage

Purpose: allocate scarce deep-research bandwidth.

Allowed outputs:

```text
FULL_V5
WATCH
REJECT
```

Quick Triage must never output `HC`.

## Stage 4 — V5 Full Deep Research

Invoke the exact frozen V5 constitution.

Required decision outputs include at minimum:

```text
Specific S-Curve
S-Curve Archetype
P1 — 36m industry inflection
P2 — winner/value-capture probability
P3 — market under-recognition
P4 — forward fundamental 3× path
Expectation Gap
3× Fundamental Burden
Tail-Risk Overlay
Critical Vetoes
Kill Criteria
Monitoring Dashboard
Strongest Counter-Thesis
Final Classification
```

## Stage 5 — Research State Registry

Persist decisions rather than relying on chat memory.

Canonical logical stores:

```text
Industry Radar
Candidate Ledger
Research State
HC Registry
Decision / Execution State
Historical Snapshots
```

Every state mutation should retain:

```text
first_discovered
last_updated
research_cutoff
source/evidence provenance
previous state
new state
reason for transition
```

Historical state is append-only / snapshot-based.

## Stage 6 — Execution

Feed the latest V5 result into:

`skills/investment-execution/industry_analysis_execution_skill_v1.md`

State machine:

```text
WATCH
→ INITIATE
→ VALIDATE
→ PYRAMID
→ HOLD
→ HARVEST
→ EXIT
```

The position clock follows the thesis clock, not vice versa.

## Stage 7 — Weekly Decision Loop

Each weekly cycle should answer only what changed:

```text
1. Which industries are NEW / UPGRADED / WEAKENING / INVALIDATED?
2. Which companies are newly recalled or cross-channel confirmed?
3. Which candidates enter V5 NOW / V5 BATCH / WATCH?
4. Which existing V5 theses gained or lost evidence?
5. Did any P1–P4 value materially change?
6. Did Expectation Gap or 3× Burden cross a decision threshold?
7. Did any Veto / Kill Criterion trigger?
8. What execution state changes follow?
9. What evidence would cause the next state transition?
```

Output a delta report rather than rewriting evergreen research.

## Source-of-truth rule

- **Frozen methodology:** pinned upstream skill artifacts listed in `OS_MANIFEST.md`.
- **Mutable runtime implementation/state:** `longgold888evan/industry-research-os`.
- **Cross-project governance / durable personal knowledge:** `longgold888evan/evan-ai-os`.
