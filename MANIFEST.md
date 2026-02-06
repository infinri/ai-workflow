# AI Knowledge Base — MANIFEST

## Purpose

This file is the **navigation index** for the AI Knowledge Base ("Coding Bible").

It maps **common tasks and problem types** to the **minimum set of documents** that should be consulted before proposing a solution.

This file is not a rulebook and does not contain guidance itself.  
It exists to **direct attention efficiently and safely**.

---

## How to Use This Manifest

When given a task:

1. Identify the **primary task type**
2. Locate the matching section below
3. Consult the listed documents **before** proposing a plan
4. Explicitly state which documents were consulted

Do **not** read unrelated sections.

---

## Read First (Always)

These documents establish global context and assumptions:

- `/OVERVIEW.md` — Complete directory index
- `/bible/architecture/principles.md` 
- `/rules/CORE_PRINCIPLES.md` — DRY, SOLID, KISS, Composition

---

## AI Workflow

Consult when:
- understanding AI assistant behavior expectations
- reviewing AI-generated code

Read:
- `/enforcement/ai-checklist.md`
- `/prompts/cascade-best-practices.md`

---

## Task → Guidance Map

### Architecture & Design Decisions
Consult when:
- introducing new modules
- changing system boundaries
- modifying core flows

Read:
- `/bible/architecture/principles.md` 

---

### Framework Development
Consult when:
- working with specific frameworks
- extending framework functionality
- following framework conventions

Read:
- `/bible/frameworks/`

---

### Database / MySQL
Consult when:
- writing or modifying queries
- diagnosing performance issues
- handling transactions or migrations

Read:
- `/bible/database/sql-authoring.md` 

---

### Security
Consult when:
- handling user input
- working with auth, ACLs, or sessions
- touching sensitive data
- exposing new endpoints

Read:
- `/bible/security/` 

---

### Performance & Scalability
Consult when:
- optimizing slow paths
- addressing memory or CPU issues
- introducing caching or async behavior

Read:
- `/bible/performance/profiling.md` 

---

### Error Handling & Reliability
Consult when:
- changing error behavior
- handling failures
- improving resiliency

Read:
- `/bible/languages/php/error-handling.md`
- `/bible/languages/php/coding-standards.md` 

---

### Testing
Consult when:
- adding tests
- refactoring with risk
- addressing regressions

Read:
- `/bible/testing/unit-testing.md` 

---

### Common Workflows (Playbooks)
Consult when:
- following a known scenario

Read:
- `/bible/playbooks/` 

---

## If You Cannot Find Guidance

If no section clearly applies:
1. State that explicitly
2. Ask for clarification
3. Propose a conservative approach

Do not infer undocumented rules.

---

## Maintenance Notes

- This file should remain **concise and scannable**
- Adding a new Bible document usually requires updating this MANIFEST
- If a section grows too large, split it and update references here
