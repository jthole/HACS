# Human-AI Collaboration Specification (HACS)

**Release:** 0.3.0<br>
**Status:** Working specification  
**Release date:** 2026-07-24<br>
**Primary owner:** HACS Maintainer

HACS is a model-agnostic specification for making sustained human-AI collaboration explicit, reviewable, and maintainable. It defines how collaboration expectations are expressed, how project-specific rules are applied, how uncertainty and task state are communicated, and how the specification itself is governed.

Version 0.3.0 adds a general applicability-and-evidence requirement for information whose correctness may depend on version, edition, configuration, or date. Git remains the canonical persistence layer; external project or assistant source stores are context caches, not authoritative repositories.

## Repository map

| Path | Purpose | Normative status |
|---|---|---|
| [`docs/PROJECT.md`](docs/PROJECT.md) | Product definition, scope, governance, and document ownership | Normative |
| [`docs/Architecture.md`](docs/Architecture.md) | HACS conceptual architecture and conformance model | Normative |
| [`docs/CollaborationProfile.md`](docs/CollaborationProfile.md) | Default human-AI collaboration requirements | Normative |
| [`docs/DecisionLog.md`](docs/DecisionLog.md) | Accepted architectural and governance decisions | Normative for accepted decisions |
| [`docs/RELEASE_PROCESS.md`](docs/RELEASE_PROCESS.md) | Versioning, review, release, and maintenance process | Normative |
| [`docs/Backlog.md`](docs/Backlog.md) | Candidate future work | Informative |
| [`docs/REVIEW_LOG.md`](docs/REVIEW_LOG.md) | Review evidence and outcomes | Informative evidence |
| [`docs/CHANGELOG.md`](docs/CHANGELOG.md) | User-visible release history | Informative |
| [`docs/MAINTENANCE_REPORT.md`](docs/MAINTENANCE_REPORT.md) | v0.3.0 maintenance and release report | Informative |
| [`templates/`](templates/) | Reusable profile and decision templates | Supporting assets |
| [`examples/`](examples/) | Non-normative usage examples | Supporting assets |
| [`assets/`](assets/) | Future diagrams and static assets | Supporting assets |

## Core principles

1. **Observable behaviour is normative.** HACS specifies collaboration outcomes that a user can inspect; it does not depend on hidden model internals.
2. **Persistence and maintenance are separate.** Producing or revising content is different from storing it durably.
3. **Git is canonical.** Copies in project-source systems, libraries, chats, or assistant memory are caches or working context.
4. **Rules are layered.** The general profile establishes defaults; a project-specific profile may extend or explicitly override them.
5. **Uncertainty is exposed.** Material assumptions, uncertainty, limitations, and blocked work are stated rather than concealed.
6. **Normative text has one owner.** Other documents reference the authoritative source instead of duplicating requirements.
7. **Applicability is established.** Version-, edition-, configuration-, and time-dependent information is verified against appropriate evidence when it could materially affect correctness.

## Using HACS

1. Read the project and architecture documents.
2. Adopt or adapt [`templates/CollaborationProfile.template.md`](templates/CollaborationProfile.template.md).
3. Add project-specific rules in a project `PROJECT.md` or dedicated profile.
4. Record consequential design decisions using [`templates/ADR.template.md`](templates/ADR.template.md).
5. Review conformance using [`examples/ConformanceReview.example.md`](examples/ConformanceReview.example.md).

Normative keywords **MUST**, **MUST NOT**, **SHOULD**, **SHOULD NOT**, and **MAY** are interpreted as requirement levels defined by this repository in [`docs/PROJECT.md`](docs/PROJECT.md#requirement-language).

## License

No open-source license is assigned in this release. See [`LICENSE.md`](LICENSE.md).
