# Codex Engineering Methodology (CEM) Glossary

## 1. Purpose

This glossary is the authoritative source of terminology for the Codex Engineering Methodology (CEM).

It establishes the canonical definitions of architectural primitives and engineering terminology consumed throughout the methodology.

All downstream repository documents shall consume the terminology defined herein and shall not redefine, reinterpret, or extend these definitions.

---

## 2. Scope

This glossary defines:

- architectural primitives;
- canonical engineering terminology;
- invariant terminology semantics;
- concept relationships;
- glossary consumption rules.

This glossary does not define:

- engineering governance;
- engineering procedures;
- methodology architecture;
- repository implementation guidance.

Those responsibilities belong to their respective canonical source documents.

---

## 3. Architectural Primitives

### Engineering Authority

The authority responsible for discovering, analyzing, designing, specifying, and approving engineering decisions.

Engineering Authority terminates at the approved engineering-to-repository implementation boundary.

---

### Execution Authority

The authority responsible for executing approved engineering work without introducing additional engineering decisions.

Execution Authority consumes approved engineering evidence.

---

### Engineering Evidence

An approved engineering artifact that documents engineering analysis, architectural decisions, implementation intent, verification, or recommendations.

Engineering Evidence is transient unless explicitly materialized as a repository engineering record.

---

### Engineering Artifact

Any work product produced during execution of the Codex Engineering Methodology.

Engineering artifacts include both transient engineering evidence and persistent repository engineering records.

---

### Repository Engineering Record

A governed repository artifact that permanently records approved engineering information within the authoritative repository.

Repository Engineering Records are persistent producer artifacts.

---

### Repository

The authoritative version-controlled collection of governed engineering artifacts comprising the Codex Engineering Methodology.

The repository is the single source of truth for published engineering records.

---

### Engineering Lifecycle

The deterministic progression of engineering work from analysis through implementation and repository governance.

---

### Engineering State

A well-defined stage within the Engineering Lifecycle.

Each engineering artifact exists in exactly one engineering state at any point in time.

---

### Engineering Transition

A deterministic movement between engineering states performed according to approved engineering rules.

Engineering transitions shall not introduce undocumented engineering decisions.

---

### Producer

The authoritative originator of an engineering artifact or repository engineering record.

Each artifact has exactly one canonical producer.

---

### Consumer

An engineering activity, repository activity, or downstream artifact that depends upon information produced by another artifact.

Consumers shall not reinterpret approved producer content.

---

### Repository Publication

The governed act of making a repository engineering record available for downstream repository consumption.

Publication establishes repository authority.

---

### Repository Governance

The collection of rules governing repository ownership, verification, publication, and maintenance.

Repository Governance does not create engineering decisions.

---

### Engineering Continuation

The deterministic continuation of engineering work through consumption of approved engineering evidence and repository engineering records.

Continuation preserves engineering context without reinterpretation.

---

## 4. Derived Concepts

Derived concepts are compositions of one or more architectural primitives.

Derived concepts do not redefine the primitives from which they are composed.

Examples include:

- Engineering Lifecycle Architecture
- Producer–Consumer Architecture
- Repository Publication Architecture
- Repository Boundary Architecture
- Repository Implementation
- Repository Verification

---

## 5. Concept Relationships

The architectural primitives relate according to the following high-level model.

- Engineering Authority produces Engineering Evidence.
- Engineering Evidence authorizes Execution Authority.
- Execution Authority produces Repository Engineering Records.
- Repository Governance verifies Repository Engineering Records.
- Repository Publication authorizes downstream Consumers.
- Engineering Continuation consumes approved Engineering Evidence and published Repository Engineering Records.

---

## 6. Terminology Invariants

The following invariants apply throughout the Codex Engineering Methodology.

1. Every canonical term has exactly one authoritative definition.
2. Every architectural primitive has exactly one canonical owner.
3. Downstream documents shall consume glossary terminology without redefining it.
4. Derived concepts shall compose primitives but shall not alter primitive definitions.
5. Repository engineering records shall preserve approved terminology.
6. Engineering terminology shall remain deterministic across repository revisions.

---

## 7. Glossary Consumption Rules

1. This glossary is the authoritative producer of engineering terminology.
2. Downstream documents shall reference glossary terms rather than redefining them.
3. Governance documents consume glossary terminology.
4. Methodology architecture consumes glossary terminology.
5. Repository engineering records inherit glossary terminology through their governing documents.
6. Changes to glossary terminology shall originate only within this document.
7. All future Codex Engineering Methodology engineering assets shall consume the terminology defined herein as their canonical vocabulary.

---

## 8. Ownership

| Architectural Concern | Canonical Owner |
|------------------------|-----------------|
| Terminology | `codex/GLOSSARY.md` |
| Governance | `codex/GOVERNANCE.md` |
| Methodology Architecture | `codex/CEM.md` |

## Repository Mutation
Repository Mutation is the exclusive repository operation authorized to modify repository contents. It consumes approved Repository Patch Specifications and Repository Patch Updates and produces an updated authoritative repository.

## Repository Mutation Verification
Repository Mutation Verification verifies that all approved mutations were applied before downstream stages.
