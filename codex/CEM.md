# Codex Engineering Methodology (CEM)

## 1. Purpose

The Codex Engineering Methodology (CEM) is the authoritative engineering methodology governing the deterministic development, evolution, implementation, verification, and governance of repository-based engineering systems.

The methodology establishes a deterministic engineering lifecycle that separates engineering decisions from repository implementation while preserving complete traceability from engineering intent to repository engineering records.

This document defines the architecture of the methodology. It does not redefine engineering terminology or governance responsibilities established by the canonical source documents.

---

# 2. Scope

This document defines:

- the architecture of the Codex Engineering Methodology;
- the deterministic engineering lifecycle;
- engineering and execution authority boundaries;
- producer–consumer architecture;
- engineering evidence architecture;
- repository engineering record architecture;
- repository implementation architecture;
- repository governance integration;
- methodology consumption rules.

This document does not define:

- engineering terminology (owned by `codex/GLOSSARY.md`);
- governance rules (owned by `codex/GOVERNANCE.md`);
- project-specific engineering procedures;
- implementation-specific guidance.

---

# 3. Architectural Objectives

The methodology is designed to:

1. Produce deterministic engineering outcomes.
2. Preserve separation of engineering and implementation.
3. Maintain explicit producer–consumer relationships.
4. Establish the repository as the authoritative engineering system of record.
5. Enable repeatable engineering execution.
6. Support long-term repository evolution without architectural drift.

---

# 4. Architectural Foundation

The methodology is constructed upon the canonical architectural primitives defined in `codex/GLOSSARY.md`.

Those primitives provide the invariant vocabulary from which all methodology capabilities are derived.

Governance responsibilities are defined exclusively in `codex/GOVERNANCE.md`.

This document composes those concepts into a complete engineering methodology architecture.

---

# 5. Methodology Architecture

The methodology is composed of five architectural layers.

## Layer 1 — Architectural Primitives

Canonical engineering terminology and invariant concepts.

Authoritative source:

- `codex/GLOSSARY.md`

---

## Layer 2 — Governance

Authority boundaries, governance rules, publication, verification, and repository acceptance.

Authoritative source:

- `codex/GOVERNANCE.md`

---

## Layer 3 — Engineering

Engineering activities responsible for:

- discovery;
- assessment;
- architectural design;
- implementation planning;
- specification;
- verification;
- engineering approval.

Engineering produces approved engineering evidence.

---

## Layer 4 — Repository Implementation

Repository implementation materializes approved engineering evidence into governed repository artifacts.

Implementation performs no engineering analysis.

Implementation introduces no engineering decisions.

---

## Layer 5 — Repository Governance

Repository governance verifies repository implementation, accepts repository modifications, and authorizes publication.

Published repository engineering records become authoritative producer artifacts for downstream engineering activities.

---

# 6. Deterministic Engineering Lifecycle

The methodology executes according to the following deterministic lifecycle.

1. Engineering Analysis
2. Engineering Assessment
3. Engineering Design
4. Repository Implementation Planning
5. Repository Patch Specification
6. Repository Patch Verification
7. Repository Patch Update Definition
8. Engineering Approval
9. Engineering Completion Gate (ECG)
10. Repository Authoring Transition
11. Repository Implementation
12. Repository Verification
13. Repository Acceptance
14. Repository Publication
15. Repository Engineering Record
16. Downstream Consumption

Each lifecycle transition is deterministic and governed.

No engineering decisions occur after the Engineering Completion Gate.

---

# 7. Authority Architecture

The methodology recognizes three architectural authorities.

## Engineering Authority

Responsible for engineering analysis and engineering decisions.

Produces approved engineering evidence.

Terminates at the Engineering Completion Gate.

---

## Repository Implementation Authority

Responsible for repository authoring.

Consumes approved engineering evidence.

Produces repository artifacts.

Does not perform engineering.

---

## Repository Governance Authority

Responsible for repository verification, repository acceptance, publication, and lifecycle governance.

Authorizes downstream consumption.

---

# 8. Producer–Consumer Architecture

Every architectural element participates in a deterministic producer–consumer relationship.

General flow:

```text
Engineering Authority
        │
        ▼
Approved Engineering Evidence
        │
        ▼
Repository Implementation
        │
        ▼
Repository Verification
        │
        ▼
Repository Governance
        │
        ▼
Published Repository Engineering Record
        │
        ▼
Downstream Consumers
```

Each producer owns exactly one authoritative output.

Consumers shall consume producer artifacts without reinterpretation.

---

# 9. Repository Architecture

The repository contains two primary artifact classes.

## Transient Engineering Evidence

Engineering artifacts produced during engineering execution.

These artifacts support engineering activities but are not authoritative repository content unless materialized.

---

## Repository Engineering Records

Persistent governed repository artifacts.

Repository Engineering Records become authoritative after successful repository publication.

---

# 10. Repository Boundaries

The methodology establishes a single engineering-to-repository boundary.

Engineering produces engineering evidence.

Repository implementation consumes engineering evidence.

Repository governance establishes repository authority.

This boundary shall remain unique and deterministic.

---

# 11. Architectural Invariants

The following architectural invariants shall always hold.

1. Engineering terminology originates exclusively from `codex/GLOSSARY.md`.
2. Governance originates exclusively from `codex/GOVERNANCE.md`.
3. Methodology architecture originates exclusively from this document.
4. Engineering Authority terminates before repository implementation.
5. Repository implementation introduces no engineering decisions.
6. Repository Governance introduces no engineering decisions.
7. Every engineering artifact has exactly one canonical producer.
8. Every engineering artifact has at least one identifiable consumer.
9. Published repository engineering records become authoritative repository producers.
10. Repository publication establishes repository authority.

---

# 12. Consumption Rules

Consumers of this document shall:

- consume methodology architecture without redefining glossary terminology;
- consume governance concepts without redefining governance rules;
- derive engineering workflows from the architectural principles defined herein;
- preserve the deterministic lifecycle and authority boundaries.

---

# 13. Canonical Dependency Model

This document depends upon:

- `codex/GLOSSARY.md`
- `codex/GOVERNANCE.md`

The following repository assets derive from this document:

- engineering workflows;
- engineering lifecycle documentation;
- engineering execution documentation;
- repository implementation guidance;
- repository governance procedures;
- future engineering assets.

---

# 14. Ownership

| Architectural Concern | Canonical Owner |
|------------------------|-----------------|
| Methodology Architecture | `codex/CEM.md` |
| Engineering Lifecycle | `codex/CEM.md` |
| Authority Architecture | `codex/CEM.md` |
| Producer–Consumer Architecture | `codex/CEM.md` |
| Repository Boundary Architecture | `codex/CEM.md` |
| Methodology Consumption Rules | `codex/CEM.md` |