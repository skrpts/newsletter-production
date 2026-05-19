# Release Notes

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
