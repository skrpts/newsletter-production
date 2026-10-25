# Release Notes

## v2.0.16
GH#1100 consumer wave (batch 4) — declare the data flow this workflow was resolving positionally.

Each stage below now receives its input through a declared `bindings:` entry instead of `default_from_previous`, which K-073 revoked. **The value is unchanged**: each binding names the step that actually produces what the stage consumes. What changes is that the dependency is stated rather than inferred from position, so a reorder can no longer silently feed a stage the wrong artefact.

Bindings added:
  `polish-language` ← `source: from_step "Newsletter Writing"` (step 3)

Dependency pins moved to the published versions that declare these slots:
  `editorial-style-guide` 1.0.1 → 1.0.2
  `polish-language` 1.0.1 → 1.0.7

## v2.0.15
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v2.0.14
GH#745 — declare per-step `output: {name, type}` on every execution step (ideas/list, newsletter_draft/text, polished_newsletter/text, subject_lines/list). Lights up the #744 rich flow-map with named, typed outputs. Content-only; no bindings or logic changes.

## v2.0.13
GH#645 Row 3b — migrate to K-037 dep-referenced schema. Strip 6 inline shared-content files and declare 6 hub-shared deps (UUID id + slug name + version + checksum from `gen-dep-checksums.mjs`). Closes pre-Step-3 inline-vendoring for this bundle.

## v2.0.12
Wave 2: re-signed with canonical engine signing pipeline.

## v2.0.11
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v2.0.10
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v2.0.9
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v2.0.8
Pipeline extraction fix — release notes now correctly appear in GitHub Release body and version registration.

## v2.0.7
First release with structured release notes. Release notes infrastructure (GH#554) now extracts notes from RELEASE_NOTES.md at publish time.

## v2.0.6
Added RELEASE_NOTES.md stub. Engine version constraint updated to >=0.1.0.

## v2.0.5
Declared `data_handling: [pii]` in manifest. Newsletter workflows are audience-adjacent — declaring PII is the honest trust signal.

## v2.0.4
Engine version constraint updated from >=1.0.0 to >=0.1.0. Fixes false "version mismatch" warning on import.

## v2.0.3
Restored manifest `id` field. Without it, the App couldn't reconcile Hub imports against existing locally-installed nodes.

## v2.0.2
Empty context bindings replaced with sensible defaults. Shared file sync.

## v2.0.1
Version bump for empty context binding fixes (GH#511).

## v2.0.0
Complete pipeline rebuild. Old pipeline had no actual newsletter writing step — it generated topic ideas and headlines but never wrote a newsletter. New 4-step pipeline: topic ideation, newsletter writing, language polish, subject line generation.

## v1.1.14
Release notes unavailable for this version.
