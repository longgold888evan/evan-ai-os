# IntelliJ Fine-grained Versioning Plugin

Goal: automatic fine-grained source-code versioning inside IntelliJ IDEA.

Architecture: PSI listener and snapshot generation; custom VersionStore; Diff comparison; Tool Window UI for history, preview, comparison, and rollback.

Constraint: do not rely on Local History API.
