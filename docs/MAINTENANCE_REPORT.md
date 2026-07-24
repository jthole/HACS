# HACS v0.3.0 Maintenance Report

**Document owner:** Release Manager  
**Status:** Informative  
**Release:** 0.3.0<br>
**Report date:** 2026-07-24

## Release summary

HACS 0.3.0 adds a general, model- and vendor-agnostic requirement for information whose correctness may depend on software or product version, edition, configuration, or current date.

The collaborator determines whether those factors are material before verification is required. When they are material, the collaborator identifies the applicable context, verifies current information, prefers authoritative evidence, distinguishes documented behaviour and public evidence from inference, avoids invented configuration details, and reports incomplete evidence.

## Baseline and version decision

The canonical baseline is commit `6f833b4`, HACS v0.2.0. The requested requirement is a backward-compatible normative addition rather than a correction that leaves requirements unchanged. ADR-0007 and [`RELEASE_PROCESS.md`](RELEASE_PROCESS.md#versioning-policy) therefore require the minor version 0.3.0.

## Requirement ownership

[`CollaborationProfile.md`](CollaborationProfile.md#13-establish-applicability-and-evidence) is the single normative owner of the observable behavioural requirement.

- ADR-0009 records the lasting decision and its consequences.
- `Architecture.md` references the owning behavioural rule as an architectural principle.
- the collaboration-profile template points adopters to the default rule without reproducing it.
- informative release documents describe the user-visible change.

## Modified documents

| Document | Change |
|---|---|
| `README.md` | Updated release metadata, summary, repository map, and core principles. |
| `LICENSE.md` | Updated release metadata; licensing terms are unchanged. |
| `docs/CollaborationProfile.md` | Added the applicability-and-evidence requirement and related anti-pattern. |
| `docs/DecisionLog.md` | Added accepted ADR-0009. |
| `docs/Architecture.md` | Added a reference to the behavioural requirement. |
| `docs/PROJECT.md` | Updated release-wide metadata. |
| `docs/RELEASE_PROCESS.md` | Updated release-wide metadata; process requirements are unchanged. |
| `docs/Backlog.md` | Updated release-wide metadata. |
| `docs/CHANGELOG.md` | Added the 0.3.0 release entry. |
| `docs/REVIEW_LOG.md` | Recorded version-classification and ownership review evidence. |
| `docs/MAINTENANCE_REPORT.md` | Replaced the 0.2.0 report with this release-specific report. |
| `templates/CollaborationProfile.template.md` | Added a reference for project-specific applicability context and sources. |
| `assets/README.md` | Updated release metadata. |
| root bootstrap documents | Removed obsolete 0.1.0 copies superseded by the authoritative files under `docs/`. |

## Assumptions

1. Commit `6f833b4` is the canonical v0.2.0 baseline.
2. HACS remains a private working specification.
3. The repository owner controls acceptance, commit, tagging, and any distribution.
4. The current English-language documents remain authoritative.
5. A canonical public repository URL and public license remain unresolved.

## Validation performed

The final validation results for this working tree are recorded in [`REVIEW_LOG.md`](REVIEW_LOG.md). Checks cover required files, local Markdown links, release metadata, decision reflection, requirement ownership, whitespace errors, and package contents.

## Known limitations

- no canonical repository URL is assigned, so changelog comparison links remain explicit placeholders;
- no public license or contribution policy is selected;
- repository validation is local rather than continuous integration;
- no machine-readable profile schema exists;
- conformance testing remains illustrative rather than comprehensive.

## Persistence status

This working tree is not a released canonical Git state. HACS v0.3.0 becomes `Released` only after maintainer approval, a release commit, and identification in Git according to [`RELEASE_PROCESS.md`](RELEASE_PROCESS.md#8-persist-and-identify). Any distribution archive must correspond to that approved Git state.
