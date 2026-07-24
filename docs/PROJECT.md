# HACS Project Definition

**Document owner:** HACS Maintainer  
**Status:** Normative  
**Version:** 0.2.0  
**Last updated:** 2026-07-23

## Purpose

This document defines HACS as a product: its objectives, scope, governance, repository model, document authorities, and completion criteria. It does not duplicate collaboration behaviour or release mechanics; those are owned by the referenced documents.

## Product statement

The Human-AI Collaboration Specification (HACS) provides a model-agnostic framework for sustained collaboration between a human and an AI system. It makes expectations explicit and reviewable without relying on access to hidden reasoning, proprietary model architecture, or a specific vendor product.

## Objectives

HACS aims to:

- reduce ambiguity about roles, authority, task state, and expected behaviour;
- improve continuity across sessions and tools;
- make consequential assumptions and uncertainty visible;
- separate content maintenance from durable persistence;
- enable project-level specialization without losing general defaults;
- create auditable evidence through decisions, reviews, and releases.

## Scope

HACS covers:

- human and AI collaboration roles;
- behavioural requirements visible in outputs and actions;
- rule precedence and project-specific profiles;
- document authority and repository governance;
- release, review, and maintenance practices;
- conformance assessment based on observable evidence.

HACS does not standardize:

- hidden chain-of-thought or internal model reasoning;
- model training, safety policy implementation, or vendor internals;
- authentication, authorization, or data-protection controls;
- a universal prompt syntax;
- claims that an AI can perform asynchronous work when the execution environment does not support it;
- automated enforcement tooling in this release.

## Stakeholders and roles

| Role | Responsibility |
|---|---|
| **Repository owner** | Owns the repository, publication rights, and licensing decision. |
| **HACS Maintainer** | Maintains release coherence, resolves editorial defects, and executes the release process. |
| **Technical Editor** | Ensures clarity, terminology consistency, structure, and cross-reference quality. |
| **Systems Architect** | Owns the conceptual model and evaluates architectural consequences. |
| **Reviewer** | Evaluates conformance, contradictions, omissions, and release readiness. |
| **Profile owner** | Defines and approves collaboration requirements for a specific person or project. |
| **AI collaborator** | Operates under the applicable profile and reports limitations and task state truthfully. |

One person or system may perform several roles, but the responsibilities remain distinct.

## Requirement language

The terms below define requirement levels in normative HACS documents:

- **MUST / MUST NOT**: mandatory for conformance;
- **SHOULD / SHOULD NOT**: expected unless a documented reason justifies deviation;
- **MAY**: optional.

Lowercase uses of these words are ordinary prose. Examples and templates are non-normative unless a document explicitly states otherwise.

## Canonical persistence

Git is the canonical persistence layer for HACS. A release is authoritative only when its files are committed or otherwise preserved as an immutable Git state, normally by an annotated tag.

Chat histories, project-source stores, assistant libraries, memory systems, generated download locations, and local temporary directories MAY support collaboration, but they MUST NOT be treated as the sole authoritative copy.

Content maintenance and content persistence are separate responsibilities:

- **maintenance** creates, edits, reviews, and validates content;
- **persistence** stores an approved state durably and identifies it unambiguously.

## Document authority and ownership

| Document | Primary responsibility | Owner | Authority |
|---|---|---|---|
| `PROJECT.md` | Product scope and governance | HACS Maintainer | Normative |
| `Architecture.md` | Concepts, layers, precedence, conformance | Systems Architect | Normative |
| `CollaborationProfile.md` | Default collaboration behaviour | Profile owner | Normative |
| `DecisionLog.md` | Accepted decisions and consequences | HACS Maintainer | Normative for accepted decisions |
| `RELEASE_PROCESS.md` | Versioning and release controls | Release Manager | Normative |
| `Backlog.md` | Candidate work | HACS Maintainer | Informative |
| `CHANGELOG.md` | Release history | Release Manager | Informative |
| `REVIEW_LOG.md` | Review evidence | Reviewer | Informative evidence |
| `MAINTENANCE_REPORT.md` | Release-specific maintenance summary | Release Manager | Informative |

When documents conflict, the conflict MUST be resolved rather than silently interpreted. Until corrected, the following precedence applies:

1. an accepted Decision Log entry addressing the exact issue;
2. `PROJECT.md` for product and governance matters;
3. `Architecture.md` for structural and conformance matters;
4. `CollaborationProfile.md` for default behavioural matters;
5. `RELEASE_PROCESS.md` for release mechanics.

This precedence is an exception-handling mechanism, not permission to leave contradictions in place.

## Rule layering

A collaboration context consists of a general profile plus optional project-specific rules. Project-specific rules MAY extend the general profile. They MAY override it only when the override is explicit, scoped, and does not falsely claim capabilities or bypass higher-order platform constraints.

Detailed precedence is defined in [`Architecture.md`](Architecture.md#rule-precedence).

## Change governance

A change requires a Decision Log entry when it:

- changes a normative principle or document responsibility;
- changes rule precedence or conformance criteria;
- introduces a compatibility-breaking requirement;
- changes the canonical persistence model;
- resolves a material ambiguity with lasting architectural consequences.

Editorial corrections, clearer examples, and non-normative backlog updates do not require a new decision unless they change meaning.

## Release completion criteria

A HACS release is complete only when:

1. all required repository documents exist;
2. versions and dates are internally consistent;
3. normative requirements are not materially duplicated;
4. internal cross references resolve;
5. accepted decisions are reflected in affected documents;
6. the review log records release validation;
7. the changelog describes user-visible changes;
8. a maintenance report records assumptions, limitations, and recommendations;
9. the repository can be packaged from a clean working tree;
10. the release is persisted in Git according to [`RELEASE_PROCESS.md`](RELEASE_PROCESS.md).

## Related documents

- [`Architecture.md`](Architecture.md)
- [`CollaborationProfile.md`](CollaborationProfile.md)
- [`DecisionLog.md`](DecisionLog.md)
- [`RELEASE_PROCESS.md`](RELEASE_PROCESS.md)
