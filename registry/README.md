# Registry

This directory provides machine-readable navigation for durable knowledge promotion.

## Authority rule

`registry/` is an **index**, not a competing source of truth.

- `OS_MANIFEST.md` remains authoritative for canonical/frozen/source-of-truth governance.
- The actual knowledge/skill/workflow file remains authoritative for its content.
- `registry/knowledge_registry.yaml` helps agents discover promoted assets and review stale items.

If the registry conflicts with the underlying artifact or `OS_MANIFEST.md`, fix the registry.

## Knowledge registry

`knowledge_registry.yaml` should contain only durable or promotion-relevant assets, not every file in the repository.

Recommended fields:

```yaml
id:
path:
kind:
domain:
first_promoted:
last_reviewed:
review_trigger:
status_note:
```

Do not duplicate secrets, long content, or full decision text into the registry.
