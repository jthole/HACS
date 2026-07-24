# HACS Architecture

**Document owner:** Systems Architect  
**Status:** Normative  
**Version:** 0.3.0<br>
**Last updated:** 2026-07-24

## Purpose

This document defines the conceptual architecture of HACS: its layers, principal concepts, rule precedence, collaboration lifecycle, state model, and conformance approach.

## Architectural drivers

HACS is designed around the following constraints:

- AI products and models differ in capability and implementation;
- internal reasoning is generally unavailable or unsuitable as an audit interface;
- collaboration may span multiple sessions and context stores;
- a generated artifact is not durably persisted merely because it appeared in a chat;
- project requirements may differ from general user preferences;
- overclaiming task execution or future work damages trust.

## Architectural principles

1. **Observable behaviour over implementation.** Conformance is evaluated using outputs, actions, artifacts, and declared state.
2. **Explicit authority.** Roles, governing documents, and rule precedence are identifiable.
3. **Single normative source.** A requirement is owned by one normative document and referenced elsewhere.
4. **Layered specialization.** General rules remain stable while projects add scoped requirements.
5. **Truthful state reporting.** Completed, pending, blocked, and externally required work are distinguished.
6. **Capability realism.** A collaborator MUST NOT claim unsupported persistence, background execution, or tool access.
7. **Applicable evidence.** Information that may vary by version, edition, configuration, or date is handled according to the evidence requirements in [`CollaborationProfile.md`](CollaborationProfile.md#13-establish-applicability-and-evidence).
8. **Traceable evolution.** Consequential changes are recorded as decisions and released through a controlled process.

## Conceptual layers

| Layer | Question answered | Primary document |
|---|---|---|
| **Governance** | What is HACS, who owns it, and what is authoritative? | [`PROJECT.md`](PROJECT.md) |
| **Architecture** | How are collaboration rules structured and evaluated? | This document |
| **Behaviour** | What observable conduct is expected by default? | [`CollaborationProfile.md`](CollaborationProfile.md) |
| **Process** | How are changes reviewed, released, and maintained? | [`RELEASE_PROCESS.md`](RELEASE_PROCESS.md) |
| **Evidence** | What decisions and reviews support the current state? | [`DecisionLog.md`](DecisionLog.md), [`REVIEW_LOG.md`](REVIEW_LOG.md) |

## Principal concepts

### Collaboration context

The set of applicable instructions, artifacts, capabilities, constraints, and current task information used for a collaboration episode.

### Collaboration profile

A versioned set of observable behavioural expectations. The repository profile provides defaults; a project profile can specialize them.

### Project rule

A scoped requirement tied to a named project, repository, or workstream. Project rules should state their scope and whether they extend or override a default.

### Capability boundary

A limitation imposed by the model, runtime, connected tools, access rights, safety controls, or execution environment. Capability boundaries take precedence over requested behaviour: HACS cannot require a system to perform an unavailable action.

### Persistence target

A storage location intended to preserve approved content. In HACS, Git is canonical; other targets are caches or transport mechanisms unless explicitly promoted by a future decision.

### Observable evidence

An output, action result, artifact, repository state, or explicit status statement that can be inspected without access to hidden model reasoning.

## Collaboration lifecycle

A conforming collaboration normally follows six stages:

1. **Establish context** — identify the task, applicable profile, project rules, sources, and capability boundaries.
2. **Frame the work** — distinguish task execution from design discussion, behavioural testing, or explanation.
3. **Plan proportionately** — create a plan when the work is multi-step, consequential, or likely to exceed a single simple action.
4. **Execute and update** — perform available work, report material findings, and expose significant changes of scope.
5. **Validate** — check outputs against requirements, sources, cross references, and completion criteria.
6. **Persist or hand off** — store the approved result in the canonical target, or state precisely what external action remains.

The lifecycle is not a mandatory conversational script. Simple work MAY compress several stages, provided the required behaviour remains observable.

## Task-state model

HACS uses four task-state labels when explicit status is useful:

| State | Meaning |
|---|---|
| **DONE** | The stated work is completed and, where applicable, the artifact or action result is available. |
| **PENDING** | Work remains and can continue within the current collaboration, but has not yet completed. |
| **BLOCKED** | Work cannot continue because of a capability, dependency, missing input, or external failure. |
| **ACTION REQUIRED** | A named external action by the human or another system is necessary. |

A collaborator MUST NOT label work `DONE` merely because it has described a plan. `PENDING` MUST NOT imply asynchronous background execution unless the environment actually supports and schedules it.

## Rule precedence

Applicable rules are evaluated in this order:

1. non-negotiable platform, legal, security, safety, and capability constraints;
2. explicit current-task instructions;
3. project-specific rules and the project's `PROJECT.md`;
4. the general Collaboration Profile;
5. general HACS process defaults;
6. non-normative examples and inferred preferences.

Within the same level, the more specific and more recent explicit rule normally prevails. A lower-level rule MUST NOT claim to override a capability boundary. Material conflicts MUST be surfaced and resolved or documented.

## Scope-change control

A material scope change occurs when the requested output, affected repository area, assumptions, risk, or completion criteria change enough to alter the plan. The collaborator SHOULD state such a change and its consequences. Minor editorial refinements do not require scope-change reporting.

## Assumptions and uncertainty

An assumption is **material** when a different value could change the solution, risk, cost, or user decision. Material assumptions MUST be stated. Uncertainty MUST be calibrated: the collaborator should distinguish verified facts, reasoned inference, and unresolved uncertainty.

## Persistence architecture

The persistence flow is:

```text
Working context -> maintained artifact -> review -> canonical Git state -> optional context-cache copy
```

A chat attachment, temporary sandbox path, or project-source copy is not by itself a canonical release. The release process defines the Git handoff and tagging requirements.

## Conformance model

HACS conformance is assessed against observable evidence.

### Conformance targets

A review MAY evaluate:

- a collaboration response or sequence;
- a project profile;
- a repository release;
- an artifact-generation workflow;
- an AI-enabled operating procedure.

### Conformance classes

| Class | Meaning |
|---|---|
| **Conformant** | All applicable MUST requirements are met; deviations from SHOULD requirements are justified. |
| **Conditionally conformant** | No known mandatory breach, but evidence is incomplete or an external dependency remains. |
| **Non-conformant** | At least one applicable MUST requirement is violated. |
| **Not assessable** | Available evidence is insufficient to determine applicability or outcome. |

Conformance does not certify correctness of every substantive answer. It evaluates adherence to the collaboration specification.

## Extension points

Future releases may add:

- machine-readable profiles;
- automated linting and link validation;
- capability declarations;
- structured conformance test suites;
- mappings to organizational governance frameworks.

Extensions MUST preserve the distinction between observable requirements and implementation internals unless a future decision explicitly changes the architecture.

## Related documents

- [`PROJECT.md`](PROJECT.md)
- [`CollaborationProfile.md`](CollaborationProfile.md)
- [`DecisionLog.md`](DecisionLog.md)
- [`RELEASE_PROCESS.md`](RELEASE_PROCESS.md)
