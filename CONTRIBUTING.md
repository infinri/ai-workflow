# Coding Bible — Contributing Guide

## Purpose

This document defines **how rules and guidance are added to the Coding Bible**.

It exists to ensure that:
- rules are structured consistently
- rules are machine-addressable at scale
- intent is preserved exactly as provided
- both humans and AI can add rules safely

This process applies equally to:
- engineers adding rules manually
- AI adding rules on behalf of engineers

---

## Authority Model

### Human Authority

All rules originate from **explicit human intent**.

A rule may only be added when a human:
- provides the rule content directly, or
- explicitly instructs the AI to record a rule

### AI Role

The AI acts as a **structural assistant**, not an author.

The AI may:
- format rules
- assign rule IDs
- apply tags and metadata
- place rules in the correct location
- request clarification if information is missing

The AI may **not**:
- invent new rules
- infer unstated constraints
- add exceptions or rationale not provided
- merge or split rules without instruction

---

## When to Add a Rule

A rule should be added when at least one of the following is true:
- a mistake has occurred more than once
- a constraint is non-obvious
- a framework behavior is surprising
- violating the guidance causes real risk
- architectural intent must be preserved

Do **not** add rules for:
- obvious language syntax
- personal style preferences
- temporary experiments
- speculative best practices

---

## Rule Placement

Rules must be placed under the appropriate domain directory:

Examples:
- Database rules → `bible/database/`
- Magento rules → `bible/magento/`
- Security rules → `bible/security/`
- Architecture rules → `bible/architecture/`

If a rule spans multiple domains:
- place it in the most specific domain
- cross-reference it from others if needed

---

## Rule Metadata (Required)

All enforceable guidance in this Bible is expressed as **explicit rule blocks**.

Each rule block **must** include its own metadata and must be independently identifiable, searchable, and extractable.

Metadata applies to the **rule itself**, not the file.

---

### Rule Boundaries

Every rule **must** be wrapped in explicit START / END markers.

```md
<!-- RULE START: DB-TXN-001 -->
## Rule DB-TXN-001
...
<!-- RULE END: DB-TXN-001 -->
