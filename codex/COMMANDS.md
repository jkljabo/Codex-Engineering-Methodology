# Command Framework

## Purpose

The Command Framework defines the canonical command architecture of the Codex Engineering Methodology (CEM). It specifies how engineering work is requested, authorized, executed, verified, and consumed while preserving deterministic engineering principles.

This document is the authoritative definition of command behavior. It defines command semantics only. Architectural terminology is owned by `GLOSSARY.md`, governance by `GOVERNANCE.md`, methodology architecture by `CEM.md`, and workflow execution by `WORKFLOW.md`.

---

# Scope

The Command Framework governs:

- command taxonomy;
- command lifecycle;
- command authority;
- command execution semantics;
- producer–consumer command relationships;
- command invariants;
- command completion gates;
- command consumption rules.

It does not redefine methodology architecture, governance, or workflow.

---

# Command Taxonomy

Every command belongs to exactly one canonical command type.

## Review

Purpose:

Evaluate existing repository evidence without modifying repository content.

Produces engineering evidence suitable for downstream consumers.

Typical outputs include:

- assessments;
- inventories;
- verification reports;
- architectural analyses;
- readiness reports.

---

## Implement

Purpose:

Materialize previously approved engineering decisions.

Implement commands consume approved engineering evidence and produce implementation artifacts without introducing new engineering decisions.

Typical outputs include:

- implementation packages;
- repository patch specifications;
- repository patch updates;
- repository-ready repository source documents.

---

## Verify

Purpose:

Confirm that a producer artifact satisfies its approved acceptance criteria.

Verification does not redesign or extend engineering evidence.

Typical outputs include:

- verification reports;
- conformance assessments;
- implementation validation.

---

## Engineering Correction

Purpose:

Resolve engineering defects or incomplete producer artifacts discovered during execution.

Engineering Correction restores deterministic execution without expanding approved scope.

---

# Command Lifecycle

Every command progresses through the following canonical lifecycle.

1. Command Requested
2. Command Authorized
3. Command Executed
4. Engineering Completion Gate (ECG)
5. Command Published
6. Consumed by Immediate Downstream Command

Commands are immutable after publication.

---

# Command Authority

Engineering authority defines **what** shall be produced.

Implementation authority defines **how approved engineering evidence is materialized**.

Command execution shall never transfer engineering authority into implementation.

No command may redefine approved engineering evidence.

---

# Command Execution Semantics

Every command shall:

- consume only approved upstream evidence;
- produce a single authoritative output;
- preserve deterministic execution;
- avoid execution-time engineering decisions;
- identify its immediate downstream consumer;
- preserve engineering and implementation authority boundaries.

---

# Producer–Consumer Relationships

Every command is both:

- a consumer of approved engineering evidence; and
- a producer of authoritative engineering evidence.

Each produced artifact shall identify its immediate downstream consumer.

Producer–consumer relationships shall be:

- deterministic;
- acyclic;
- complete;
- uniquely traceable.

---

# Command Invariants

The following invariants apply to every command.

- A command consumes only approved engineering evidence.
- Engineering authority precedes implementation authority.
- Every artifact has one authoritative producer.
- Every artifact has one immediate downstream consumer.
- Commands shall not redefine approved architectural primitives.
- Commands shall not introduce execution-time engineering decisions.
- Repository publication occurs only after Engineering Completion Gate approval.
- Published engineering evidence is immutable until superseded through an approved engineering process.

---

# Engineering Completion Gates

Every command shall conclude with an Engineering Completion Gate (ECG).

The ECG verifies:

- required producer artifacts were consumed;
- command objectives were satisfied;
- deterministic execution was preserved;
- authority boundaries remained intact;
- downstream consumption is authorized.

Only a passing ECG authorizes publication.

---

# Command Consumption Rules

Consumers shall:

- consume only approved engineering evidence;
- consume only authoritative producer artifacts;
- preserve upstream engineering intent;
- avoid reinterpretation of approved evidence;
- identify all consumed artifacts;
- identify the next valid downstream command.

Consumers shall not:

- infer missing engineering evidence;
- redesign approved engineering decisions;
- bypass required producer artifacts;
- alter published engineering evidence.

---

# Repository Publication Boundary

Engineering evidence becomes repository content only after successful completion of the Engineering Completion Gate.

This boundary separates engineering decision making from repository implementation and preserves deterministic execution.

---

# Relationships to Foundational Documents

| Document | Responsibility |
|-----------|----------------|
| `GLOSSARY.md` | Canonical terminology |
| `GOVERNANCE.md` | Governance rules and repository authority |
| `CEM.md` | Methodology architecture |
| `WORKFLOW.md` | Workflow execution model |
| `COMMANDS.md` | Command architecture and execution semantics |

Each responsibility is unique and non-overlapping.

---

# Compliance

All future engineering assets that define executable methodology behavior shall conform to this Command Framework.

No downstream engineering asset may redefine command taxonomy, lifecycle, authority, execution semantics, or command invariants established by this document.