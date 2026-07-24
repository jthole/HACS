# HACS v0.2.0 Maintenance Report

**Document owner:** Release Manager  
**Status:** Informative  
**Release:** 0.2.0  
**Report date:** 2026-07-23

## Release summary

HACS 0.2.0 converts the 0.1.0 bootstrap into a coherent, reviewable specification. The release preserves the three original architectural decisions and supplies the missing governance, architecture, behaviour, release, review, template, and example structure needed for practical maintenance.

The release is intentionally model- and vendor-agnostic. Observable behaviour, truthful task-state reporting, capability realism, explicit assumptions, rule layering, and Git-first persistence form the core.

## Baseline assessment

The supplied 0.1.0 archive contained ten small root-level files and three accepted decisions:

1. Git is the canonical persistence layer.
2. Document maintenance and persistence are separate responsibilities.
3. Observable behaviour is normative.

The bootstrap did not yet define document ownership, precedence, conformance, versioning, quality gates, or a release process.

## Modified documents

| Document | Change |
|---|---|
| `README.md` | Rewritten as repository entry point with principles, map, and usage guidance. |
| `LICENSE.md` | Clarified private-use, all-rights-reserved status. |
| `.gitignore` | Expanded for operating-system, editor, build, archive, and temporary files. |
| `docs/PROJECT.md` | Expanded into the normative product and governance definition. |
| `docs/Architecture.md` | Added layers, concepts, lifecycle, task state, rule precedence, persistence flow, and conformance. |
| `docs/CollaborationProfile.md` | Expanded bootstrap bullets into a complete normative default profile. |
| `docs/DecisionLog.md` | Converted to ADR format; preserved ADR-0001–0003 and added ADR-0004–0008. |
| `docs/Backlog.md` | Structured and prioritized future work; reconciled bootstrap items. |
| `docs/CHANGELOG.md` | Added complete 0.2.0 history and compatibility statement. |
| `docs/REVIEW_LOG.md` | Added release-wide validation evidence and open notes. |
| `docs/RELEASE_PROCESS.md` | New normative release and maintenance process. |
| `docs/MAINTENANCE_REPORT.md` | New release maintenance report. |
| `templates/*` | Added reusable profile, ADR, and release-checklist templates. |
| `examples/*` | Added non-normative profile and conformance-review examples. |
| `assets/README.md` | Defined asset purpose and current absence of binary assets. |

## Architectural decisions

### Preserved

- ADR-0001: Git is canonical.
- ADR-0002: maintenance and persistence are separate.
- ADR-0003: observable behaviour is normative.

### Added

- ADR-0004: layered document authority;
- ADR-0005: single ownership of normative requirements;
- ADR-0006: explicit scoped project-profile overrides;
- ADR-0007: semantic versioning;
- ADR-0008: capability boundaries outrank requested behaviour.

## Assumptions

1. The supplied ZIP is the complete canonical 0.1.0 baseline available for this release task.
2. HACS remains a private working specification in 0.2.0.
3. The repository owner will perform the final Git commit and tag because no direct canonical repository integration is available in this execution context.
4. The English-language document set is authoritative; no translation is included.
5. GitHub-compatible Markdown is sufficient; no static-site generator is required.

## Validation performed

- required repository paths and files checked;
- internal Markdown file targets checked;
- release-version metadata checked;
- accepted bootstrap decisions compared with all normative documents;
- cross-document terminology and ownership reviewed;
- ZIP archive generated from a clean release directory;
- archive manifest and SHA-256 checksum generated outside the repository for delivery verification.

## Known limitations

- no canonical repository URL is assigned;
- no public license or contribution policy is selected;
- no automated CI or Markdown linter is included;
- no machine-readable profile schema exists;
- conformance testing is illustrative rather than comprehensive;
- no direct Git commit or tag was possible from the supplied archive alone;
- external platform safety and capability constraints are referenced conceptually rather than standardized.

## Recommendations for 0.3.0

1. Add a normative glossary and stabilize definitions.
2. Create a complete observable conformance test catalogue.
3. Define and prototype a machine-readable profile schema.
4. Add automated repository linting and release packaging.
5. Add several real project-profile case studies, including explicit overrides.
6. Decide licensing and contribution governance before public distribution.
7. Assign a canonical repository URL and replace changelog placeholders.
8. Evaluate a capability declaration that can state persistence and automation support without coupling HACS to a vendor.

## Persistence handoff

The delivered ZIP is a packaged release candidate. To make it canonical, extract it into the repository, review the diff, commit it, and create the `v0.2.0` annotated tag according to [`RELEASE_PROCESS.md`](RELEASE_PROCESS.md#8-persist-and-identify).
