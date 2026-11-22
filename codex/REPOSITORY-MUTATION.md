# Repository Mutation

## 1. Purpose

This document is the authoritative source governing Repository Mutation within the Codex Engineering Methodology (CEM).

Its purpose is to define the canonical repository operation responsible for transforming approved engineering intent into authoritative repository state while preserving deterministic execution, repository governance, and producer–consumer traceability.

Repository Mutation is an execution activity. It does not perform engineering analysis, introduce engineering decisions, or reinterpret approved engineering evidence.

---

## 2. Scope

This document defines:

- Repository Mutation;
- Repository Mutation Verification;
- repository mutation authority boundaries;
- mutation lifecycle;
- producer–consumer relationships;
- repository-state transition requirements;
- mutation invariants; and
- mutation consumption rules.

This document does not define:

- engineering terminology;
- engineering governance;
- methodology architecture;
- engineering workflow;
- engineering approval.

Those responsibilities remain with their canonical source documents.

---

## 3. Authority

This document is subordinate to:

- `codex/GLOSSARY.md` for terminology;
- `codex/CEM.md` for methodology architecture;
- `codex/GOVERNANCE.md` for repository governance; and
- `codex/WORKFLOW.md` for workflow sequencing.

Repository Mutation shall not redefine architectural primitives established by those documents.

---

## 4. Repository Mutation

Repository Mutation is the exclusive repository operation authorized to modify repository contents.

Repository Mutation shall:

- consume only approved repository engineering artifacts;
- apply approved repository modifications deterministically;
- preserve repository structure;
- preserve repository formatting;
- preserve repository addressability;
- preserve repository traceability;
- preserve repository governance.

Repository Mutation shall not:

- introduce engineering decisions;
- reinterpret approved engineering artifacts;
- alter architectural intent;
- create new governance concepts.

---

## 5. Repository Mutation Lifecycle

The canonical mutation lifecycle is:

```text
Published Repository Patch Specifications
                ↓
Approved Repository Patch Updates
                ↓
Repository Mutation
                ↓
Updated Authoritative Repository
                ↓
Repository Mutation Verification
                ↓
Downstream Repository Operations
```

No alternate mutation lifecycle is authoritative.

---

## 6. Producer–Consumer Relationships

| Producer | Consumer |
|----------|----------|
| Published Repository Patch Specifications | Repository Mutation |
| Approved Repository Patch Updates | Repository Mutation |
| Repository Mutation | Updated Authoritative Repository |
| Updated Authoritative Repository | Repository Mutation Verification |
| Repository Mutation Verification | Repository Asset Generation |
| Repository Mutation Verification | Repository Closeout |
| Repository Mutation Verification | Commit Readiness |

Repository Mutation consumes only approved producer artifacts.

Repository Mutation Verification consumes only repository state.

---

## 7. Authority Boundaries

Engineering Authority terminates prior to Repository Mutation.

Repository Mutation performs repository execution only.

Repository Mutation Verification validates repository state only.

Neither operation is authorized to introduce engineering decisions.

---

## 8. Repository Mutation Invariants

The following invariants always apply:

1. Repository Mutation is the exclusive repository-state modification operation.
2. Repository Mutation consumes only approved engineering artifacts.
3. Repository Mutation introduces no engineering decisions.
4. Repository Mutation preserves repository structure.
5. Repository Mutation preserves repository formatting.
6. Repository Mutation preserves repository addressability.
7. Repository Mutation preserves producer–consumer traceability.
8. Repository Mutation Verification validates repository state independently.
9. Downstream repository operations consume only verified repository state.
10. Repository Mutation remains deterministic.

---

## 9. Repository Mutation Verification

Repository Mutation Verification confirms:

- every approved mutation has been applied;
- every modified repository artifact is repository-addressable;
- repository structure is preserved;
- repository formatting is preserved;
- repository traceability is preserved;
- no unintended repository modifications occurred.

Repository Mutation Verification is the authoritative consumer of Repository Mutation.

---

## 10. Consumption Rules

Downstream repository operations shall consume only verified repository state.

Repository Asset Generation, Repository Closeout, Repository Commit, and other repository execution activities shall not consume Repository Mutation directly.

Repository Mutation Verification establishes the repository-state boundary for downstream execution.

---

## 11. Engineering Completion Gate (ECG)

Repository Mutation is complete only when:

- approved Repository Patch Specifications were consumed;
- approved Repository Patch Updates were consumed;
- repository mutation completed successfully;
- Repository Mutation Verification passed;
- no engineering decisions were introduced; and
- deterministic producer–consumer relationships remain intact.

ECG Status: PASS