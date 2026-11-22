# State Framework

**Document Status:** Canonical  
**Authority:** Codex Engineering Methodology (CEM)  
**Document Owner:** Engineering Authority  
**Consumes:** `GLOSSARY.md`, `GOVERNANCE.md`, `CEM.md`, `WORKFLOW.md`, `COMMANDS.md`, `EXECUTION.md`  
**Consumed By:** All engineering assets requiring deterministic engineering state management

---

# 1. Purpose

The State Framework defines the canonical engineering state architecture for the Codex Engineering Methodology (CEM).

It establishes the authoritative model governing engineering state, state ownership, state transitions, lifecycle progression, and state consumption. This document is the sole authoritative definition of engineering state semantics throughout the methodology.

---

# 2. Scope

This document defines:

- canonical engineering states;
- engineering state lifecycle;
- state ownership;
- state authority;
- state transitions;
- state invariants;
- producer–consumer state relationships;
- state dependency rules; and
- state consumption rules.

This document does not define workflow execution, command execution, governance policy, execution architecture, or architectural primitives.

---

# 3. State Lifecycle

Engineering progresses through the following deterministic lifecycle:

```
Planned
    ↓
Reviewed
    ↓
Approved
    ↓
Implemented
    ↓
Verified
    ↓
Completed
```

Each engineering activity shall occupy exactly one state.

State transitions shall occur only through approved deterministic progression.

---

# 4. Canonical Engineering States

## Planned

Engineering work has been identified and authorized for analysis.

Producer:
Engineering Planning

Consumer:
Engineering Review

---

## Reviewed

Engineering analysis has completed.

Engineering evidence has been produced.

Producer:
Engineering Review

Consumer:
Engineering Approval

---

## Approved

Engineering Authority has accepted the engineering evidence.

Repository implementation may begin.

Producer:
Engineering Authority

Consumer:
Repository Implementation

---

## Implemented

Approved engineering decisions have been materialized within the repository.

Producer:
Repository Implementation

Consumer:
Engineering Verification

---

## Verified

Engineering verifies repository implementation exactly matches approved engineering evidence.

Producer:
Engineering Verification

Consumer:
Repository Completion

---

## Completed

Engineering activity is complete.

The engineering record becomes immutable except through approved governance.

Producer:
Engineering Completion

Consumer:
Future Engineering Activities

---

# 5. Engineering Authority

Engineering Authority owns:

- engineering state definitions;
- state lifecycle;
- state transition authorization;
- state invariants;
- state governance.

Repository Implementation Authority owns:

- repository materialization only.

Implementation Authority shall never redefine engineering state.

---

# 6. State Transition Rules

Every transition shall:

1. be deterministic;
2. preserve engineering authority;
3. preserve implementation authority;
4. preserve producer–consumer relationships;
5. preserve repository traceability;
6. consume approved engineering evidence;
7. introduce no new engineering decisions.

State transitions may never be skipped.

---

# 7. State Invariants

The following invariants always apply.

**SI-01**

Every engineering activity has exactly one current state.

**SI-02**

Every state has exactly one authoritative owner.

**SI-03**

State ownership is unique.

**SI-04**

Engineering Authority exclusively authorizes state transitions.

**SI-05**

Repository Implementation Authority never creates engineering evidence.

**SI-06**

Producer–consumer relationships remain deterministic.

**SI-07**

State progression is acyclic.

**SI-08**

Engineering evidence is immutable after approval except through approved governance.

---

# 8. Producer–Consumer State Model

Engineering state follows the canonical producer–consumer chain.

```
Planning
      │
      ▼
Review
      │
      ▼
Approval
      │
      ▼
Repository Implementation
      │
      ▼
Verification
      │
      ▼
Completion
```

Every producer creates evidence consumed by exactly one downstream engineering activity.

Consumers shall never reinterpret approved engineering evidence.

---

# 9. Dependencies

This document depends upon:

- `GLOSSARY.md`
- `GOVERNANCE.md`
- `CEM.md`
- `WORKFLOW.md`
- `COMMANDS.md`
- `EXECUTION.md`

No dependency cycles are permitted.

---

# 10. Consumption Rules

Consumers of this document shall:

- consume engineering state definitions without modification;
- preserve state ownership;
- preserve state lifecycle semantics;
- preserve state invariants;
- preserve producer–consumer relationships;
- preserve engineering authority boundaries;
- preserve implementation authority boundaries.

No downstream engineering asset may redefine engineering state.

---

# 11. Repository Implementation Constraints

Repository implementations derived from this document shall:

- preserve the approved State Framework unchanged;
- introduce no architectural primitives;
- introduce no execution-time engineering decisions;
- preserve deterministic engineering;
- preserve repository traceability;
- preserve engineering authority;
- preserve implementation authority boundaries.

---

# Engineering Completion Gate (ECG)

Repository implementation of this document is complete only when:

- every engineering state has been defined;
- state ownership is unique;
- lifecycle progression is deterministic;
- transition rules are complete;
- state invariants are complete;
- producer–consumer relationships are deterministic;
- dependency relationships are acyclic;
- consumption rules are complete; and
- no engineering decisions have been introduced beyond the approved engineering evidence.