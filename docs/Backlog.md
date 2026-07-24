# HACS Backlog

**Author:** Johan Thole <jthole@gmail.com><br>
**Document owner:** HACS Maintainer  
**Status:** Informative  
**Version:** 0.4.0<br>
**Last updated:** 2026-07-24

## Purpose

This backlog records candidate work. An item is not a commitment and has no normative force until accepted through the normal decision and release process.

## Prioritization

| Priority | Meaning |
|---|---|
| **P1** | Important for the next planned release |
| **P2** | Valuable but not release-critical |
| **P3** | Exploratory or dependent on future evidence |

## Candidate items

| ID | Priority | Candidate outcome | Rationale / dependency | Target |
|---|---|---|---|---|
| BL-001 | P1 | Add a normative glossary | Reduce ambiguity in recurring terms without scattering definitions | Unscheduled |
| BL-002 | P1 | Define machine-readable collaboration-profile schema | Enable validation and tooling while preserving Markdown as human-readable source | Unscheduled |
| BL-003 | P1 | Create a conformance test catalogue | Turn behavioural requirements into repeatable observable tests | Unscheduled |
| BL-004 | P1 | Add repository linting | Validate links, metadata, versions, duplicate headings, and normative keywords | Unscheduled |
| BL-005 | P2 | Define capability declaration format | Allow environments to state supported tools, persistence, and automation | Future |
| BL-007 | P2 | Define contribution process and code of conduct | Needed before accepting public contributions | Before public release |
| BL-008 | P2 | Add GitHub Actions release workflow | Automate validation and packaging after lint rules stabilize | Future |
| BL-009 | P2 | Add worked project-profile examples | Demonstrate inheritance, extensions, and explicit overrides | Unscheduled |
| BL-010 | P3 | Map HACS to organizational AI-governance frameworks | Avoid premature coupling; requires stable core concepts | Future |
| BL-011 | P3 | Evaluate context-cache synchronization guidance | Clarify safe refresh patterns without promoting caches to canonical status | Future |
| BL-012 | P1 | Reassess release versioning and draft-release policy | Clarify version classification for derived artifacts, licensing changes, and pre-release working states | Future |
| BL-013 | P1 | Define a repeatable contract-synchronization workflow | Ensure every MINOR release updates `CollaborationContract.md` consistently from changed owning design documents | Before next MINOR release |

## Removed or completed bootstrap items

- **Evaluate Library behaviour:** resolved architecturally by classifying assistant libraries and project sources as context caches; product-specific behaviour may still be documented in examples.
- **Add glossary:** retained as BL-001.
- **GitHub integration:** refined into BL-008; Git is canonical independently of hosting provider.
- **Evaluate standard open-source licenses:** completed by the repository owner's adoption of CC BY-SA 4.0 for the draft specification.

## Intake criteria

A backlog item SHOULD state a user or maintainer problem, expected outcome, dependencies, and likely affected documents. Architectural work requires a Decision Log entry before becoming normative.
