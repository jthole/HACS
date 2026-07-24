# HACS Release Process

**Document owner:** Release Manager  
**Status:** Normative  
**Version:** 0.3.0<br>
**Last updated:** 2026-07-24

## Purpose

This document defines how HACS changes are planned, reviewed, versioned, packaged, persisted, and maintained.

## Versioning policy

HACS uses semantic versioning:

- **MAJOR** — incompatible changes to normative requirements, precedence, or conformance;
- **MINOR** — backward-compatible normative additions, substantial clarifications, or new document capabilities;
- **PATCH** — backward-compatible corrections that do not materially change requirements.

Pre-release identifiers such as `0.3.0-rc.1` MAY be used. The version is release-wide; individual documents MUST carry the release version unless explicitly versioned independently by a future decision.

## Release states

| State | Meaning |
|---|---|
| **Planned** | Scope and target version identified. |
| **In development** | Documents are being changed and are not release-ready. |
| **Release candidate** | Intended content is complete and under final validation. |
| **Packaged** | A reproducible archive has been produced and checked. |
| **Released** | The approved state is committed and identified in canonical Git, normally with an annotated tag. |
| **Superseded** | A later release replaces it for current use. |

A downloadable ZIP is `Packaged`, not automatically `Released`.

## Release workflow

### 1. Establish baseline

The Release Manager MUST identify the canonical source revision. Imported archives MUST be inventoried before changes begin.

### 2. Plan release scope

The plan SHOULD identify:

- target version and rationale;
- intended outcomes;
- affected documents;
- required architectural decisions;
- assumptions, risks, and dependencies;
- completion and review criteria.

### 3. Perform impact analysis

Each normative change MUST be evaluated across all affected documents. The maintainer MUST avoid isolated changes that leave contradictory requirements or stale references.

### 4. Record decisions

Changes meeting the criteria in [`PROJECT.md`](PROJECT.md#change-governance) MUST be recorded in [`DecisionLog.md`](DecisionLog.md) and reflected in all affected documents.

### 5. Maintain documents

The Technical Editor and Systems Architect update content according to document ownership. Obvious editorial improvements MAY be applied without separate approval when they do not change meaning.

### 6. Review

The release MUST pass the quality gates below. Review evidence is recorded in [`REVIEW_LOG.md`](REVIEW_LOG.md).

### 7. Package

The packaged release MUST contain the repository root directory and required structure. Generated archives SHOULD use `HACS_v<version>.zip` and SHOULD exclude local temporary or build files.

### 8. Persist and identify

The repository owner or authorized maintainer MUST commit the approved state to Git. The recommended tag is `v<version>` and SHOULD be annotated with a concise release summary.

Example:

```bash
git add .
git commit -m "Release HACS v0.2.0"
git tag -a v0.2.0 -m "HACS v0.2.0"
```

A remote push is optional for private use but SHOULD be performed when a remote is the operational backup.

### 9. Publish or distribute

Distribution artifacts MUST correspond to the tagged Git state. If a ZIP was produced before the final commit, it SHOULD be regenerated from the tag.

### 10. Maintain

Post-release defects are logged in the backlog. Material corrections follow the versioning policy rather than silently replacing released content.

## Quality gates

A release candidate MUST satisfy:

### Content

- required files exist;
- each normative document states purpose, owner, status, and version;
- terminology and requirement language are consistent;
- no accepted decision is contradicted;
- normative requirements have one primary owner;
- assumptions and known limitations are recorded.

### Validation

- local cross references resolve;
- Markdown is suitable for GitHub rendering;
- release version and date are consistent;
- changelog and maintenance report are complete;
- examples are marked non-normative;
- archive contents match the intended repository structure.

### Governance

- consequential decisions are logged;
- review outcomes are recorded;
- license status is explicit;
- canonical-persistence responsibility is clear.

## Hotfix process

A critical non-breaking defect MAY use a PATCH release with reduced planning, but all mandatory quality gates still apply. A hotfix MUST NOT rewrite an existing tagged release.

## Release rollback

Git history MUST be preserved. A defective release MAY be marked superseded or withdrawn from distribution, but its tag and decision history SHOULD remain available for audit unless removal is legally or operationally required.

## Release checklist

A reusable checklist is provided in [`../templates/ReleaseChecklist.template.md`](../templates/ReleaseChecklist.template.md).
