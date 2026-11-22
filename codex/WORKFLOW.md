# Codex Engineering Methodology (CEM) Workflow

## 1. Purpose

This document is the authoritative source for workflow execution within the Codex Engineering Methodology (CEM).

Its purpose is to define the canonical engineering workflow used to execute deterministic engineering activities while preserving engineering authority, implementation authority, repository governance, and complete producer–consumer traceability.

This document defines **how engineering is executed**. It does not redefine engineering terminology, governance responsibilities, or methodology architecture established by the canonical source documents.

---

# 2. Scope

This document defines:

- the canonical engineering workflow;
- workflow stages;
- workflow state transitions;
- engineering authority transitions;
- implementation authority transitions;
- producer–consumer workflow relationships;
- engineering completion gates;
- workflow invariants;
- workflow consumption rules.

This document does not define:

- engineering terminology;
- governance policy;
- methodology architecture;
- repository implementation content;
- engineering asset content.

---

# 3. Authority

This document is subordinate to:

- `codex/GLOSSARY.md` for engineering terminology;
- `codex/GOVERNANCE.md` for governance;
- `codex/CEM.md` for methodology architecture.

No document may redefine workflow concepts established herein.

---

# 4. Canonical Workflow

The Codex Engineering Methodology executes through a deterministic sequence of workflow stages.

Each stage:

- has a single architectural purpose;
- has one canonical producer;
- produces one authoritative output;
- has one or more deterministic downstream consumers;
- introduces engineering decisions only within its defined authority.

The canonical workflow is:

```text
Discovery
    ↓
Assessment
    ↓
Planning
    ↓
Specification
    ↓
Verification
    ↓
Engineering Completion Gate
    ↓
Repository Implementation
    ↓
Repository Verification
    ↓
Repository Governance
    ↓
Published Repository Engineering Record
```

No workflow execution may bypass or reorder these stages unless explicitly authorized by methodology architecture.

---

# 5. Workflow Stages

## 5.1 Discovery

Purpose:

Establish engineering context.

Produces:

- discovery evidence.

Consumes:

- repository evidence.

---

## 5.2 Assessment

Purpose:

Analyze the current engineering state.

Produces:

- assessment evidence.

Consumes:

- approved discovery evidence.

---

## 5.3 Planning

Purpose:

Define the approved engineering intent.

Produces:

- implementation planning artifacts.

Consumes:

- approved assessment evidence.

---

## 5.4 Specification

Purpose:

Define deterministic implementation contracts.

Produces:

- implementation specifications.

Consumes:

- approved planning artifacts.

---

## 5.5 Verification

Purpose:

Verify that implementation intent is complete, deterministic, and internally consistent.

Produces:

- verification evidence.

Consumes:

- approved implementation specifications.

---

## 5.6 Engineering Completion Gate

Purpose:

Terminate engineering decision making.

Produces:

- approved engineering evidence.

Consumes:

- approved verification evidence.

No engineering decisions may be introduced beyond this gate.

---

## 5.7 Repository Implementation

Purpose:

Materialize approved engineering decisions within the repository.

Produces:

- repository source documents;
- repository engineering records;
- approved repository modifications.

Consumes:

- approved engineering evidence.

Repository implementation shall not introduce new engineering decisions.

---

## 5.8 Repository Verification

Purpose:

Verify repository implementation.

Produces:

- repository verification evidence.

Consumes:

- completed repository implementation.

---

## 5.9 Repository Governance

Purpose:

Accept repository implementation for authoritative downstream consumption.

Produces:

- published repository engineering records.

Consumes:

- approved repository verification evidence.

---

# 6. Workflow State Transitions

Workflow transitions are deterministic.

Each workflow state may consume only approved outputs from its immediate predecessor.

No workflow state may consume unpublished engineering evidence.

Workflow transitions are:

| From | To |
|------|----|
| Discovery | Assessment |
| Assessment | Planning |
| Planning | Specification |
| Specification | Verification |
| Verification | Engineering Completion Gate |
| Engineering Completion Gate | Repository Implementation |
| Repository Implementation | Repository Verification |
| Repository Verification | Repository Governance |

No alternate transition path is authoritative.

---

# 7. Engineering Authority Transitions

Engineering authority exists only during engineering execution.

| Authority | Begins | Ends |
|-----------|--------|------|
| Engineering Authority | Discovery | Engineering Completion Gate |
| Repository Implementation Authority | Repository Implementation | Repository Verification |
| Repository Governance Authority | Repository Governance | Publication |

Authority transitions occur only at defined workflow boundaries.

Authorities shall not overlap.

---

# 8. Producer–Consumer Workflow

Each workflow stage is both a consumer and a producer.

| Producer | Immediate Consumer |
|----------|--------------------|
| Discovery | Assessment |
| Assessment | Planning |
| Planning | Specification |
| Specification | Verification |
| Verification | Engineering Completion Gate |
| Engineering Completion Gate | Repository Implementation |
| Repository Implementation | Repository Verification |
| Repository Verification | Repository Governance |
| Repository Governance | Downstream Engineering Activities |

Consumers shall consume approved outputs without reinterpretation.

---

# 9. Engineering Completion Gates

The workflow contains three canonical completion gates.

## Engineering Completion Gate (ECG)

Confirms engineering work is complete.

Authorizes transition into repository implementation.

---

## Repository Acceptance Gate (RAG)

Confirms repository implementation faithfully materializes approved engineering evidence.

Authorizes repository governance.

---

## Repository Publication Gate (RPG)

Authorizes repository engineering records for downstream consumption.

Published repository engineering records become authoritative repository evidence.

---

# 10. Workflow Invariants

The following invariants shall always hold.

1. Every workflow stage has one canonical purpose.

2. Every workflow stage has one canonical producer.

3. Every workflow output has an identifiable downstream consumer.

4. Engineering authority terminates before repository implementation.

5. Repository implementation introduces no engineering decisions.

6. Repository governance introduces no engineering decisions.

7. Published repository engineering records become authoritative repository evidence.

8. Workflow execution remains deterministic.

9. Workflow execution remains acyclic.

10. Workflow execution preserves complete producer–consumer traceability.

---

# 11. Workflow Consumption Rules

All downstream engineering assets shall consume this workflow without redefining:

- workflow stages;
- workflow sequencing;
- authority transitions;
- completion gates;
- workflow invariants.

Engineering assets may define asset-specific deliverables but shall not redefine workflow architecture.

Repository implementation activities shall materialize approved engineering decisions only.

Repository governance shall publish approved repository engineering records only.

---

# 12. Relationship to Canonical Source Documents

The foundational CEM source documents have distinct responsibilities.

| Document | Canonical Responsibility |
|----------|---------------------------|
| `codex/GLOSSARY.md` | Engineering terminology |
| `codex/GOVERNANCE.md` | Governance rules and authority |
| `codex/CEM.md` | Methodology architecture |
| `codex/WORKFLOW.md` | Engineering workflow execution |

Each architectural concept has exactly one authoritative owner.

---

# Engineering Completion Gate (ECG)

Repository implementation verification confirms:

- approved Workflow Architecture Assessment consumed;
- approved Repository Implementation Package consumed;
- no new engineering decisions introduced;
- deterministic workflow preserved;
- engineering authority boundaries preserved;
- implementation authority boundaries preserved;
- repository governance boundaries preserved;
- single engineering-to-repository publication boundary preserved.

**Engineering Completion Gate: PASS**

---

## Next Valid Command

**Epic:** CEM-R – Repository Governance

**Engineering Activity:** Repository Implementation Foundation

**Stage:** Repository Foundation Verification

**Repository:** Authoritative Repository (Current CEM-WIP.zip)

**Attachment Required:** Current CEM-WIP.zip

**Objective:**

Using only:

- the authoritative repository;
- `codex/GLOSSARY.md`;
- `codex/GOVERNANCE.md`;
- `codex/CEM.md`; and
- `codex/WORKFLOW.md`,

verify that the four canonical source documents establish a complete architectural and execution foundation for the Codex Engineering Methodology.

Produce only:

- Repository Foundation Verification Report;
- Architectural Ownership Matrix;
- Workflow Integration Assessment;
- Cross-Document Dependency Verification;
- Repository Foundation Readiness Assessment.

Apply the Engineering Completion Gate (ECG) prior to publication.

End with the **Next Valid Command**.

## Repository Mutation
Repository Mutation is the exclusive repository operation authorized to modify repository contents. It consumes approved Repository Patch Specifications and Repository Patch Updates and produces an updated authoritative repository.

## Repository Mutation Verification
Repository Mutation Verification verifies that all approved mutations were applied before downstream stages.
