# Changelog

**Document owner:** Release Manager  
**Status:** Informative  
**Current release:** 0.3.0

All notable changes to HACS are recorded here. HACS follows the versioning rules in [`RELEASE_PROCESS.md`](RELEASE_PROCESS.md#versioning-policy).

## [0.3.0] — 2026-07-24

### Added

- a general applicability-and-evidence requirement for information that may vary by version, edition, configuration, or date;
- ADR-0009, establishing material dependence as the trigger for current verification;
- explicit requirements to prefer authoritative evidence, distinguish evidence from inference, avoid invented configuration details, and disclose incomplete applicability evidence.

### Changed

- updated the architectural principles and collaboration-profile template to reference the new normative behaviour;
- removed obsolete root-level bootstrap documents whose authoritative successors are under `docs/`;
- advanced release-wide metadata to 0.3.0.

### Compatibility

This is a backward-compatible normative addition. The minor version increment follows ADR-0007 and the versioning policy in `RELEASE_PROCESS.md`.

## [0.2.0] — 2026-07-23

### Added

- complete governance model and document ownership in `PROJECT.md`;
- layered conceptual architecture, lifecycle, rule precedence, task-state model, and conformance classes;
- expanded normative default Collaboration Profile;
- ADR structure and five new architectural decisions;
- formal release process with semantic versioning and quality gates;
- maintenance report for the release;
- reusable collaboration-profile and ADR templates;
- non-normative profile and conformance-review examples;
- placeholder asset guidance.

### Changed

- transformed the bootstrap repository into the defined `HACS/` structure;
- moved normative documents under `docs/`;
- clarified that Git is canonical while project-source and library systems are caches;
- clarified that generation, availability for download, Git persistence, and release are distinct states;
- replaced informal Decision Log notes with traceable ADR entries;
- expanded `.gitignore` for common local and generated artifacts;
- made private-use licensing status explicit.

### Fixed

- removed ambiguity about document precedence and ownership;
- resolved duplication between project, architecture, and behavioural concerns;
- established consistent version metadata and cross references;
- prevented unsupported asynchronous-work claims from being treated as conformant behaviour.

### Compatibility

This is a backward-compatible expansion of the 0.1.0 bootstrap principles. Existing decisions ADR-0001 through ADR-0003 remain accepted and are elaborated, not reversed.

## [0.1.0] — 2026-07-23

### Added

- initial bootstrap repository;
- canonical Git persistence principle;
- separation of document maintenance and persistence;
- observable-behaviour principle;
- minimal project, architecture, profile, backlog, review, and changelog files.

[0.2.0]: https://example.invalid/hacs/releases/tag/v0.2.0
[0.1.0]: https://example.invalid/hacs/releases/tag/v0.1.0
[0.3.0]: https://example.invalid/hacs/releases/tag/v0.3.0

> The comparison links are placeholders until a canonical repository URL is assigned.
