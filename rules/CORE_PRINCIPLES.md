# Core Coding Principles

## Purpose

This document defines **fundamental coding principles** that apply globally to all work in this codebase.

These are **universal best practices** that guide code quality, maintainability, and design decisions.

---

## 1. DRY (Don't Repeat Yourself)

- **Single Source of Truth**: Every piece of knowledge must have a single, unambiguous representation
- **Code Reusability**: Extract duplicate logic into reusable functions, classes, or modules
- **Centralization**: Common functionality must exist in one location only
- **Action**: Before writing new code, search existing codebase for similar implementations
- **Refactoring**: When encountering duplicate code, consolidate it immediately

---

## 2. SOLID Principles

### S - Single Responsibility Principle
- Each class/function must have one and only one reason to change
- One class = one responsibility = one job
- **Action**: If describing a class requires "and", it likely violates SRP

### O - Open/Closed Principle
- Software entities should be open for extension, closed for modification
- Use interfaces, abstract classes, and dependency injection
- **Action**: Extend behavior through new classes, not by modifying existing ones

### L - Liskov Substitution Principle
- Derived classes must be substitutable for their base classes
- Child classes must not break parent class contracts
- **Action**: Ensure subclasses can replace parent classes without altering correctness

### I - Interface Segregation Principle
- Clients should not depend on interfaces they don't use
- Create focused, specific interfaces rather than monolithic ones
- **Action**: Split large interfaces into smaller, role-specific ones

### D - Dependency Inversion Principle
- Depend on abstractions, not concretions
- High-level modules should not depend on low-level modules
- **Action**: Inject dependencies through constructors/methods, use interfaces/abstractions

---

## 3. KISS (Keep It Simple, Stupid)

- **Simplicity First**: Choose the simplest solution that solves the problem
- **Avoid Over-Engineering**: Don't add complexity for hypothetical future needs
- **Readability**: Code should be self-documenting and obvious in intent
- **Action**: If a solution feels complex, step back and find a simpler approach

---

## 4. Composition Over Inheritance

- **Favor Composition**: Use object composition over class inheritance
- **Flexibility**: Composition provides more flexibility and reduces coupling
- **Has-A vs Is-A**: Prefer "has-a" relationships over "is-a" relationships when possible
- **Action**: Before creating inheritance hierarchies, consider if composition achieves the same goal with less coupling
