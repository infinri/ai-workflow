# AI Knowledge Base (Coding Bible)

## Purpose

This directory contains the **AI Knowledge Base ("Coding Bible")** for this repository.

It is a **structured, versioned source of institutional knowledge** that documents:
- architectural decisions and rationale
- coding standards and constraints
- framework-specific rules (e.g. Magento)
- security expectations
- performance and scalability considerations
- approved patterns and known anti-patterns

This knowledge exists to ensure that **AI-assisted work aligns with how this codebase is designed to function**.

---

## Authority & Scope

- This directory **does not grant file access**
- This directory **does not override global rules**
- This directory **does not authorize actions**
- This directory **does not enforce behavior**

All enforcement, permissions, and workflow requirements are defined elsewhere.

This directory is **reference and reasoning material only**.

---

## Required Usage Pattern (AI)

Before proposing any solution, refactor, fix, or recommendation, the AI must:

1. **Identify the task domain(s)**  
   Examples include (but are not limited to):
   - Magento dependency injection
   - Database / MySQL behavior
   - Security
   - Error handling
   - Performance optimization
   - Refactoring
   - Production incident response

2. **Consult only the relevant sections of this knowledge base**
   - Do NOT load or summarize the entire Bible
   - Use the MANIFEST to locate applicable documents
   - Prefer the smallest possible set of documents needed

3. **Explicitly state which sections were consulted**
   Example:
   > Consulted:  
   > `/bible/database/mysql-indexing.md`  
   > `/bible/magento/collections.md` 

4. **Propose a plan before requesting file access**

If guidance is unclear, conflicting, or missing, the AI **must stop and ask** before proceeding.

---

## Directory Structure

This directory is intentionally **modular and hierarchical**.

```
ai-workflow/
├── README.md            # Entry point (this file)
├── MANIFEST.md          # Navigation and index (START HERE for lookup)
├── OVERVIEW.md          # Complete directory index
├── global_rules.md      # Global AI rules
│
├── bible/               # Domain-specific knowledge
│   ├── architecture/
│   ├── database/
│   ├── frameworks/
│   ├── languages/
│   │   └── php/
│   ├── performance/
│   ├── playbooks/
│   ├── security/
│   └── testing/
│
├── enforcement/         # AI behavior enforcement
├── prompts/             # Reusable prompt templates
└── rules/               # Core principles and rules
```

Each folder represents a **decision domain**, not a language or framework tutorial.

---

## How to Find Relevant Guidance

Use the following process:

1. **Start with `MANIFEST.md`**
   - It maps common tasks to relevant sections
   - It identifies high-risk areas
   - It lists "read-first" documents

2. **Navigate to the smallest relevant subsection**
   - Do not assume cross-domain rules
   - Do not infer missing constraints
   - Do not generalize without confirmation

3. **Consult multiple domains explicitly if required**
   Example:
   - A Magento performance issue may require reading both:
     - `/bible/magento/` 
     - `/bible/database/` 

---

## What Belongs in This Knowledge Base

### Included
- Architectural decisions and tradeoffs
- Non-obvious constraints
- Framework-specific rules and limitations
- Known foot-guns
- Approved patterns
- Explicit anti-patterns
- Rationale ("why") behind decisions

### Excluded
- Generic language tutorials
- Obvious best practices
- Style preferences without architectural impact
- Rules that belong in global enforcement
- Temporary or experimental guidance

---

## Handling Gaps or Conflicts

If guidance is:
- missing
- ambiguous
- contradictory
- outdated

The AI must:
1. Call it out explicitly
2. Ask for clarification
3. Propose a conservative default

**Silent guessing is not allowed.**

---

## Guiding Principle

This knowledge base exists to:

> **Preserve architectural intent, not constrain engineering judgment.**

Engineers remain responsible for decisions.  
The AI exists to assist, not to override.
