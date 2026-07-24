# HACS v0.4.0 Maintenance Report

**Author:** Johan Thole <jthole@gmail.com><br>
**Document owner:** Release Manager  
**Status:** Informative  
**Release candidate:** 0.4.0<br>
**Report date:** 2026-07-24

## Release summary

HACS 0.4.0 adds a self-contained collaboration contract for direct adoption, an informative overview of the ten HACS principles, explicit evidence precedence across product versions and contexts, and CC BY-SA 4.0 licensing. Author metadata now identifies Johan Thole across all repository documents while role-based document ownership remains separate.

## Baseline and version decision

The canonical release baseline is commit `61530f1`, tagged `v0.3.0`. The standalone contract and principles overview are new document capabilities, and the evidence-precedence rules are a substantial backward-compatible clarification. ADR-0007 and [`RELEASE_PROCESS.md`](RELEASE_PROCESS.md#versioning-policy) therefore require the minor version 0.4.0.

The maintainer intends to reassess release versioning and draft-release policy for future versions. That work is recorded as BL-012 and does not change the current release process.

## Requirement ownership

[`CollaborationProfile.md`](CollaborationProfile.md#13-establish-applicability-and-evidence) remains the single normative owner of the default evidence-handling behaviour. It now requires:

- precedence for the newest authoritative evidence applicable to the relevant context;
- explicit handling of information from different versions or contexts;
- a warning when evidence is available only for older versions.

`CollaborationContract.md` is a self-contained contract that becomes normative when adopted in a collaboration context. Within the HACS repository, it is maintained as a standalone delivery artifact derived from the owning normative requirements.

`PRINCIPLES.md` is informative and does not own normative requirements.

ADR-0010 records this artifact classification and makes contract alignment a release check.

## Licensing and attribution

The repository owner selected the Creative Commons Attribution-ShareAlike 4.0 International license for the draft specification. `LICENSE.md` provides the license notice, canonical license links, and suggested attribution.

All repository Markdown documents identify:

> Johan Thole <jthole@gmail.com>

as author. Role-based fields such as document owner, profile owner, reviewer, and release manager remain unchanged.

## Modified documents

| Document or group | Change |
|---|---|
| `CollaborationContract.md` | Added a standalone, directly adoptable collaboration contract and version-evidence safeguards. |
| `docs/DecisionLog.md` | Added ADR-0010 for the contract's authority and alignment model. |
| `docs/CollaborationProfile.md` | Added the owning normative evidence-precedence and older-source warning requirements. |
| `docs/PRINCIPLES.md` | Added an informative overview of the ten HACS principles. |
| `LICENSE.md` | Adopted CC BY-SA 4.0 and added attribution guidance. |
| `README.md` | Updated release metadata, summary, repository map, and licensing statement. |
| `docs/Backlog.md` | Closed the license-selection item and added release-policy review item BL-012. |
| `docs/CHANGELOG.md` | Added the 0.4.0 entry. |
| `docs/REVIEW_LOG.md` | Recorded 0.4.0 validation evidence and remaining release action. |
| current-version documents | Advanced release-wide metadata to 0.4.0. |
| all Markdown documents | Added consistent author metadata. |

## Assumptions

1. Commit `61530f1` and tag `v0.3.0` identify the canonical prior release.
2. HACS remains a draft specification.
3. Johan Thole is the author and repository owner for the material being licensed.
4. The repository owner controls acceptance, commit, tagging, and distribution.
5. The current English-language documents remain authoritative.
6. Third-party material, if later added, must be identified with its applicable license.

## Validation performed

Validation covered:

- author metadata across repository Markdown documents;
- current-version and historical-version consistency;
- normative ownership of the evidence-precedence requirements;
- local Markdown files and heading anchors;
- licensing-statement consistency;
- repository structure;
- `git diff --check`.

The results are recorded in [`REVIEW_LOG.md`](REVIEW_LOG.md).

## Known limitations

- no canonical repository URL is assigned, so changelog comparison URLs remain explicit placeholders;
- no contribution policy is selected;
- repository validation is local rather than continuous integration;
- no machine-readable profile schema exists;
- conformance testing remains illustrative rather than comprehensive;
- contract synchronization is a manual release check pending the repeatable workflow in BL-013;
- the release versioning and draft-release policy is scheduled for reassessment.

## Persistence status

HACS v0.4.0 is a release candidate in the working tree. It has not been committed, tagged, packaged, pushed, or released. It becomes `Released` only after maintainer approval, a release commit, and identification in Git according to [`RELEASE_PROCESS.md`](RELEASE_PROCESS.md#8-persist-and-identify).
