# Release Notes

## v1.1.31
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v1.1.30
GH#745 — declare per-step `output: {name, type}` on every execution step (release_brief/text, release_notes/text, polished_notes/text, code_review/text, compliance_verdict/decision). Lights up the #744 rich flow-map. Content-only; no bindings or logic changes.

## v1.1.29
GH#645 Row 3b — migrate to K-037 dep-referenced schema. Strip 8 inline shared-content files and declare 8 hub-shared deps (UUID id + slug name + version + checksum from `gen-dep-checksums.mjs`). Closes pre-Step-3 inline-vendoring for this bundle.

## v1.1.28
Wave 2: re-signed with canonical engine signing pipeline.

## v1.1.27
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v1.1.26
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v1.1.25
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v1.1.24
Added review-code-changes prompt for the code-review skill in the release review parallel block.
