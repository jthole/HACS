# HACS Decision Log

**Author:** Johan Thole <jthole@gmail.com><br>
**Document owner:** HACS Maintainer  
**Status:** Normative for accepted decisions  
**Version:** 0.4.0<br>
**Last updated:** 2026-07-24

## Purpose

This log records architectural and governance decisions with lasting consequences. Accepted decisions are authoritative within their stated scope. Superseded decisions remain for traceability.

## Status values

- **Proposed** — under consideration;
- **Accepted** — governs the current release;
- **Deprecated** — retained but discouraged pending replacement;
- **Superseded** — replaced by a later decision;
- **Rejected** — considered and not adopted.

## Decision index

| ID | Title | Status | Introduced |
|---|---|---|---|
| ADR-0001 | Git is the canonical persistence layer | Accepted | 0.1.0 |
| ADR-0002 | Document maintenance and persistence are separate responsibilities | Accepted | 0.1.0 |
| ADR-0003 | Observable behaviour is normative | Accepted | 0.1.0 |
| ADR-0004 | HACS uses layered document authority | Accepted | 0.2.0 |
| ADR-0005 | Normative requirements have a single owning document | Accepted | 0.2.0 |
| ADR-0006 | Project profiles use explicit scoped overrides | Accepted | 0.2.0 |
| ADR-0007 | HACS uses semantic versioning for specification releases | Accepted | 0.2.0 |
| ADR-0008 | Capability boundaries outrank requested behaviour | Accepted | 0.2.0 |
| ADR-0009 | Material applicability determines evidence verification | Accepted | 0.3.0 |
| ADR-0010 | The standalone contract is an adoptable derived artifact | Accepted | 0.4.0 |

---

## ADR-0001 — Git is the canonical persistence layer

**Status:** Accepted  
**Context:** Collaboration may occur in chats, project-source systems, libraries, local sandboxes, or generated downloads. These locations do not provide one stable authority.  
**Decision:** Git is the canonical persistence layer for HACS. A release becomes authoritative through a durable Git commit and release identifier.  
**Consequences:** External stores are caches or transfer mechanisms. A generated file is not a canonical release until persisted in Git.  
**Affected documents:** `PROJECT.md`, `Architecture.md`, `RELEASE_PROCESS.md`

## ADR-0002 — Document maintenance and persistence are separate responsibilities

**Status:** Accepted  
**Context:** Producing correct content and storing it durably are different operations and may be performed by different actors or tools.  
**Decision:** HACS treats maintenance and persistence as separate responsibilities and reports their states independently.  
**Consequences:** Completion statements must distinguish generated, reviewed, downloadable, committed, and released states.  
**Affected documents:** `PROJECT.md`, `Architecture.md`, `CollaborationProfile.md`

## ADR-0003 — Observable behaviour is normative

**Status:** Accepted  
**Context:** HACS must remain model-agnostic and cannot depend on access to hidden reasoning or proprietary internals.  
**Decision:** HACS defines and evaluates observable behaviour, artifacts, actions, and declared task state.  
**Consequences:** Hidden chain-of-thought is outside the conformance model. Conformance evidence must be externally inspectable.  
**Affected documents:** `Architecture.md`, `CollaborationProfile.md`

## ADR-0004 — HACS uses layered document authority

**Status:** Accepted  
**Context:** The bootstrap mixed governance, architecture, behaviour, and process. That structure risks contradiction and unclear ownership.  
**Decision:** HACS separates Governance, Architecture, Behaviour, Process, and Evidence, each with a primary owning document.  
**Consequences:** Documents gain clear purpose and authority. Conflicts can be localized and resolved.  
**Affected documents:** All normative documents

## ADR-0005 — Normative requirements have a single owning document

**Status:** Accepted  
**Context:** Duplicated normative text tends to diverge across releases.  
**Decision:** Each normative requirement has one owning document. Other documents reference it or summarize it informatively without recreating a second requirement.  
**Consequences:** Editing requires release-wide impact analysis and cross-reference validation.  
**Affected documents:** All documents

## ADR-0006 — Project profiles use explicit scoped overrides

**Status:** Accepted  
**Context:** Projects need specialized collaboration rules, but implicit replacement of general preferences makes behaviour unpredictable.  
**Decision:** Project profiles inherit the default Collaboration Profile. Overrides must be explicit, scoped, and identify the changed rule.  
**Consequences:** Silence means inheritance. Project rules cannot override platform, legal, safety, security, or capability constraints.  
**Affected documents:** `PROJECT.md`, `Architecture.md`, `CollaborationProfile.md`

## ADR-0007 — HACS uses semantic versioning for specification releases

**Status:** Accepted  
**Context:** Users need to understand whether a release is editorial, additive, or compatibility-breaking.  
**Decision:** HACS uses `MAJOR.MINOR.PATCH`: MAJOR for incompatible normative changes, MINOR for backward-compatible additions or substantial clarifications, PATCH for non-breaking corrections. Pre-releases may append identifiers such as `-rc.1`.  
**Consequences:** Version selection requires impact analysis, not document-counting.  
**Affected documents:** `RELEASE_PROCESS.md`, `CHANGELOG.md`

## ADR-0008 — Capability boundaries outrank requested behaviour

**Status:** Accepted  
**Context:** A profile can request behaviour that a model or execution environment cannot perform, such as unsupported background work or direct repository writes.  
**Decision:** Capability boundaries take precedence over requested behaviour. The collaborator must state the limitation and perform the nearest honest supported action.  
**Consequences:** HACS cannot be used to require false claims or unavailable actions. Limitations become explicit evidence rather than silent failure.  
**Affected documents:** `Architecture.md`, `CollaborationProfile.md`

## ADR-0009 — Material applicability determines evidence verification

**Status:** Accepted<br>
**Context:** Information about software and other evolving products can vary by version, edition, configuration, or date. Treating all such questions as requiring current external research is wasteful, while relying on stale or assumed details can make an answer materially incorrect.<br>
**Decision:** A collaborator determines whether version, edition, configuration, or recency could materially affect correctness. When it could, the collaborator establishes the applicable context, verifies current information using authoritative evidence where available, distinguishes evidence from inference, and reports unresolved applicability or evidence limitations.<br>
**Consequences:** Verification is triggered by material dependence rather than topic category. Configuration details cannot be invented, and incomplete evidence remains visible. The default behavioural requirements are owned by `CollaborationProfile.md`.<br>
**Affected documents:** `Architecture.md`, `CollaborationProfile.md`

## ADR-0010 — The standalone contract is an adoptable derived artifact

**Status:** Accepted<br>
**Context:** Users need one self-contained contract that can be applied directly across AI products. Reproducing behavioural requirements in a delivery artifact could create a second repository owner and allow the contract to diverge from the default Collaboration Profile.<br>
**Decision:** HACS provides `CollaborationContract.md` as a self-contained derived artifact. It becomes normative within a collaboration context when adopted there. Within the HACS repository, the owning normative documents remain authoritative, and release validation must check the contract for alignment with them. `PRINCIPLES.md` is an informative overview and does not own normative requirements.<br>
**Consequences:** The contract can be used without the rest of the repository while HACS retains single ownership of its source requirements. Contract alignment becomes a release check.<br>
**Affected documents:** `PROJECT.md`, `Architecture.md`, `CollaborationContract.md`, `PRINCIPLES.md`, `RELEASE_PROCESS.md`

## Adding decisions

Use [`../templates/ADR.template.md`](../templates/ADR.template.md). New accepted decisions MUST identify affected documents and MUST be reflected in those documents before release.
