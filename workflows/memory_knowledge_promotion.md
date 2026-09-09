# Memory / Knowledge Promotion Workflow

**Status:** CANONICAL + ACTIVE  
**Purpose:** convert useful conversational/project knowledge into durable, versioned AI-OS assets without turning every chat note into source-of-truth knowledge.

## 0. Mission

The operating loop is:

```text
conversation / file / project / inbox
        ↓
CAPTURE — candidate knowledge
        ↓
CLASSIFY — what kind of thing is this?
        ↓
DRAFT — explicit artifact with provenance
        ↓
VALIDATE — evidence / reuse / conflict / sensitivity gates
        ↓
ACTIVE durable knowledge
        ↓
important choice → Decision Record
repeated method → Skill / Workflow candidate
        ↓
eval / repeated successful use
        ↓
CANONICAL
        ↓
explicit freeze decision when stability matters
        ↓
FROZEN
```

This workflow governs **promotion**, not ordinary note taking.

The OS should remain selective: useful temporary context may remain in chat, project files, or `inbox/` and never become durable knowledge.

---

# 1. Source layers

Knowledge may originate from:

```text
A. Conversation
B. Inbox note
C. File / document
D. Project work
E. External research
F. Experiment / eval result
G. Explicit user decision
H. Repeated observed working pattern
```

Source is not authority. A statement from one conversation is not automatically durable truth.

Every promoted artifact should retain enough provenance to answer:

> Where did this come from, when was it believed, and why was it promoted?

---

# 2. Classification before promotion

Every candidate should be classified before deciding where it belongs.

Allowed default kinds:

```text
FACT
PREFERENCE
MENTAL_MODEL
PRINCIPLE
DECISION
METHOD
WORKFLOW
PROJECT_CONTEXT
RESOURCE
OPEN_QUESTION
```

Routing:

```text
FACT / PREFERENCE / MENTAL_MODEL / PRINCIPLE
→ knowledge/<domain>/

DECISION
→ knowledge/decisions/

METHOD
→ initially knowledge/ or inbox
→ after repeated success: skills/

WORKFLOW
→ workflows/

PROJECT_CONTEXT
→ projects/<project>/

RESOURCE
→ relevant knowledge/resource index

OPEN_QUESTION
→ inbox/ or project backlog
```

A candidate may change kind during validation.

---

# 3. The promotion state machine

## Stage 0 — TRANSIENT

Normal chat/project context. No repository artifact is required.

Stay transient when the item is:

- useful only for the current task;
- easy to reconstruct;
- low-confidence speculation;
- duplicated elsewhere;
- likely to become stale quickly;
- too sensitive to persist safely.

## Stage 1 — CAPTURED

Create an inbox/candidate item only when the information has plausible future value.

Minimum capture fields:

```yaml
id:
created_at:
source_type:
source_ref:
kind:
domain:
summary:
why_it_might_matter:
confidence:
sensitivity:
```

At capture time, do not over-polish.

## Stage 2 — DRAFT

A candidate becomes a DRAFT artifact when it is worth making explicit and inspectable.

A draft must separate:

```text
Observed / sourced facts
User preference or explicit decision
Inference / interpretation
Open uncertainty
```

Never write inference as fact merely because it sounds plausible.

## Stage 3 — VALIDATION GATE

`VALIDATED` is a **promotion gate**, not a global lifecycle state. Passing validation normally promotes a DRAFT to ACTIVE.

Run the canonical eval in:

`evals/knowledge_promotion_eval.md`

Mandatory gates:

1. **Durability** — likely useful beyond the current task.
2. **Provenance** — source / reasoning basis is recoverable.
3. **Truth labeling** — fact, preference, decision and inference are not conflated.
4. **Conflict check** — no silent contradiction with a higher-authority artifact.
5. **Sensitivity check** — safe and appropriate to persist in the repo.
6. **Destination check** — stored in the correct domain/type.
7. **Update semantics** — append, revise, supersede or archive is explicit.

## Stage 4 — ACTIVE

ACTIVE knowledge is the OS's current durable working knowledge.

It may be changed when new evidence or an explicit new decision arrives.

ACTIVE does **not** mean infallible. It means:

> this is the current maintained representation the OS should normally use.

## Stage 5 — CANONICAL

Promote an ACTIVE artifact to CANONICAL only when the user/system explicitly chooses it as the source of truth for a named capability, framework, or contract.

Canonical promotion requires:

```text
clear scope
clear inputs / outputs or semantic responsibility
known conflict precedence
successful real use or eval
explicit source-of-truth decision
```

## Stage 6 — FROZEN

Freeze only when change control is more valuable than continuous editing.

Freeze requires:

```text
explicit freeze decision
immutable version identifier
content identity/hash when practical
upgrade rule
replacement/supersession policy
```

Never freeze merely because a file is important.

---

# 4. Decision promotion

Create a Decision Record when a conclusion changes future behavior or governance and would be expensive to rediscover.

Typical triggers:

- choose one architecture over another;
- freeze or unfreeze a framework;
- change source-of-truth location;
- choose a long-lived investment/career/learning principle;
- adopt or reject a recurring operating policy;
- make a trade-off that future agents might otherwise re-litigate.

Use:

`templates/decision_record.md`

A Decision Record should include:

```text
Context
Decision
Why
Alternatives considered
Consequences
What would change the decision
Related assets
Date / provenance
```

A Decision Record is not automatically CANONICAL; its authority follows `OS_MANIFEST.md` and the artifact it governs.

---

# 5. Method → Skill / Workflow promotion

Do not turn a one-off clever answer into a Skill.

Use this ladder:

```text
one-off technique
→ candidate METHOD
→ repeated use
→ generalized input/output contract
→ eval cases
→ DRAFT skill/workflow
→ successful use on independent cases
→ ACTIVE
→ explicit source-of-truth decision
→ CANONICAL
→ optional FROZEN
```

Default evidence for promotion to reusable Skill/Workflow:

```text
at least 2 independent successful uses
OR
1 strong production use + explicit user decision
```

A methodology with high consequence should require stronger evidence and adversarial evaluation.

Use:

`templates/skill_promotion_record.md`

---

# 6. Knowledge update semantics

When new information conflicts with existing knowledge, choose one of four operations explicitly:

```text
APPEND
→ new fact complements the old artifact

REVISE
→ current ACTIVE knowledge changes but historical Git history remains sufficient

SUPERSEDE
→ new artifact replaces an old framework/decision; old file gets replacement pointer

ARCHIVE
→ no longer current, retained for provenance
```

Never silently overwrite a FROZEN asset.

For Point-in-Time research or historical decisions, prefer immutable snapshots rather than revision.

---

# 7. Sensitivity and persistence rules

The repository must not become a credential store.

Never persist by default:

```text
passwords
API keys / access tokens
private keys
security answers
account numbers
one-time codes
raw authentication material
```

Personal or sensitive information should be promoted only when it is genuinely necessary for the OS's purpose and the repository's privacy model is appropriate.

Prefer storing a durable preference or operating constraint over unnecessary raw personal detail.

---

# 8. Conversation-to-OS protocol

At the end of a high-value conversation, an agent may perform a promotion review.

Ask internally:

```text
1. Did we discover a durable fact/preference/principle?
2. Did the user make an important decision?
3. Did we create a reusable method?
4. Did an existing ACTIVE asset become stale?
5. Did repeated cases reveal a systematic failure in a Skill?
```

Then:

```text
nothing durable
→ leave conversation transient

potentially useful but uncertain
→ inbox / candidate draft

validated durable knowledge
→ ACTIVE knowledge

important choice
→ Decision Record

reusable method
→ Skill/Workflow promotion path
```

Do not promote content merely because the conversation was long or intellectually interesting.

---

# 9. Agent write policy

When working in `evan-ai-os`, AI agents should:

1. Read `OS_MANIFEST.md` first.
2. Run a conflict/sensitivity check before promotion.
3. Use a template for new candidate/decision/skill-promotion records.
4. Prefer updating an existing ACTIVE artifact over creating duplicates.
5. Preserve explicit provenance and dates.
6. Update `registry/knowledge_registry.yaml` for promoted durable knowledge when applicable.
7. Update `OS_MANIFEST.md` only when authority/lifecycle/source-of-truth status changes.
8. Never promote a draft to CANONICAL/FROZEN without an explicit decision.

---

# 10. Minimal promotion algorithm

```text
NEW INFORMATION
      ↓
Future value?
  NO → transient
  YES
      ↓
Sensitive / unsafe to persist?
  YES → do not persist by default
  NO
      ↓
Classify kind + domain
      ↓
Duplicate / already represented?
  YES → update existing artifact
  NO  → create candidate/draft
      ↓
Run validation eval
      ↓
Fail → inbox / draft / discard
Pass → ACTIVE
      ↓
Changes future governance?
  YES → Decision Record
      ↓
Repeated generalized method?
  YES → Skill/Workflow + eval
      ↓
Explicit source-of-truth decision?
  YES → CANONICAL
      ↓
Explicit immutable baseline needed?
  YES → FROZEN
```

---

# 11. Success metric

The objective is not repository size.

A healthy AI OS maximizes:

```text
useful durable context recovered correctly
+
important decisions not re-litigated
+
reusable methods applied consistently
+
provenance / version clarity
-
noise
-
duplication
-
stale truth
-
methodology drift
```

The desired result is a **knowledge flywheel**, not a note archive.
