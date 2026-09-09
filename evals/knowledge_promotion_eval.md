# Knowledge Promotion Eval

**Status:** CANONICAL + ACTIVE  
**Used by:** `workflows/memory_knowledge_promotion.md`

## Purpose

Decide whether candidate information should remain transient, stay in draft/inbox, become ACTIVE durable knowledge, or enter the Skill/Workflow promotion path.

This eval is intentionally precision-oriented. The cost of promoting noisy or stale material is long-term context pollution.

---

## 1. Hard vetoes

Do **not** promote when any of these are true:

- contains credentials, secrets, authentication material, or unnecessary high-risk personal data;
- provenance is unknown for a factual claim that materially matters;
- conflicts with a higher-authority canonical/frozen asset and the conflict is unresolved;
- is clearly temporary task context with no durable value;
- is duplicated by an existing artifact and no update is required;
- states uncertain inference as established fact.

A vetoed item may still remain transient or be rewritten into a safer, properly labeled draft.

---

## 2. Scored dimensions

Score each dimension `0 / 1 / 2`.

| Dimension | 0 | 1 | 2 |
|---|---|---|---|
| Durability | one-off / rapidly stale | useful for weeks/months | likely useful repeatedly over long horizon |
| Reuse value | unlikely to affect future work | useful in one recurring area | materially improves many future decisions/tasks |
| Specificity | vague / generic | partially actionable | concrete enough to retrieve and apply correctly |
| Provenance | unclear | source known but weak/incomplete | source/decision/evidence trail is explicit |
| Confidence | speculative | plausible / partially validated | explicit preference/decision or strong evidence |
| Stability | likely to change soon | may change | structurally stable until explicit new evidence/decision |
| Distinctiveness | duplicates existing knowledge | partially new | adds genuinely new durable information or supersedes old state |

Maximum score: `14`.

---

## 3. Default interpretation

```text
0–5
→ TRANSIENT / DISCARD

6–8
→ CAPTURE / DRAFT

9–11
→ candidate for ACTIVE after conflict + sensitivity checks

12–14
→ strong ACTIVE candidate; consider Decision Record or reusable-method path
```

The score never overrides a hard veto.

---

## 4. Type-specific validation

### FACT

Require:

- provenance;
- time scope where relevant;
- separation from interpretation;
- update/review trigger if likely to age.

### PREFERENCE

Require that it is either:

- explicitly stated by the user; or
- repeatedly demonstrated and clearly labeled as inferred rather than asserted.

Do not store excessive personal detail merely to personalize responses.

### MENTAL_MODEL / PRINCIPLE

Require:

- a clear statement;
- intended scope;
- known limitations or counterexamples when consequential;
- evidence that it is actually used, not merely admired.

### DECISION

Require:

- context;
- decision;
- rationale;
- alternatives/trade-offs;
- what would change it.

Use a Decision Record when the choice is likely to be revisited.

### METHOD / WORKFLOW

Require:

- clear problem definition;
- inputs and outputs;
- repeatable steps;
- at least one real successful use before ACTIVE;
- independent reuse/eval before CANONICAL unless explicitly overridden by the user.

### PROJECT_CONTEXT

Require:

- project identity;
- current relevance;
- distinction between historical state and current state;
- upstream source-of-truth pointer when implementation lives elsewhere.

---

## 5. Skill / Workflow promotion gate

A method should not become a reusable Skill or Workflow because it worked once.

Default promotion test:

```text
Generalizable?
AND
Input/output contract clear?
AND
Failure modes documented?
AND
>= 2 independent successful uses
   OR 1 production-quality use + explicit user promotion decision
AND
Eval cases exist?
```

If NO, keep it as a METHOD draft or ACTIVE knowledge note.

---

## 6. Canonical promotion gate

An ACTIVE artifact becomes CANONICAL only when all are true:

```text
Named responsibility is clear
No competing source of truth remains unresolved
Real use/eval has succeeded
Mutation policy is known
Conflict precedence is known
User/system explicitly selects it as source of truth
```

Canonical status is governance, not a quality score.

---

## 7. Freeze gate

Freeze only when:

```text
canonical responsibility is stable
+
version identity exists
+
future edits would create dangerous drift
+
upgrade conditions are explicit
+
explicit freeze decision exists
```

A highly useful living document should remain `CANONICAL + ACTIVE` rather than being frozen prematurely.

---

## 8. Required eval output

For each reviewed candidate output:

```yaml
candidate_id:
kind:
domain:
score:
hard_veto: true | false
veto_reason:
proposed_action: TRANSIENT | DRAFT | ACTIVE | DECISION_RECORD | SKILL_CANDIDATE | WORKFLOW_CANDIDATE
existing_asset_to_update:
provenance_ok: true | false
conflict_check: PASS | REVIEW
sensitivity_check: PASS | REVIEW | BLOCK
reason:
next_validation_trigger:
```

For important promotions, preserve this reasoning in the commit/Decision Record rather than creating an eval log for every trivial note.
