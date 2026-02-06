# Unit Testing

## Purpose

This document defines **unit testing principles** to ensure code quality, confidence, and maintainability.

---

<!-- RULE START: TEST-TDD-001 -->
## Rule TEST-TDD-001: Test-Driven Development

**Domain**: Testing  
**Severity**: High

### Statement
Write tests before or alongside implementation:

- **Test First**: Define expected behavior before writing implementation
- **Red-Green-Refactor**: Write failing test, make it pass, then refactor
- **Coverage**: Aim for high test coverage on business logic

### Action
Every public method should have corresponding tests.

### Rationale
TDD ensures code is testable by design and provides immediate feedback on correctness.
<!-- RULE END: TEST-TDD-001 -->

---

<!-- RULE START: TEST-ISO-001 -->
## Rule TEST-ISO-001: Test Isolation

**Domain**: Testing  
**Severity**: High

### Statement
Tests must be isolated and independent:

- **Unit Tests**: Test components in isolation using mocks/stubs
- **No Shared State**: Each test must set up its own state
- **Deterministic**: Tests must produce the same result every time

### Action
Mock external dependencies; never rely on external services in unit tests.

### Rationale
Isolated tests are faster, more reliable, and pinpoint failures precisely.
<!-- RULE END: TEST-ISO-001 -->

---

<!-- RULE START: TEST-INT-001 -->
## Rule TEST-INT-001: Integration Testing

**Domain**: Testing  
**Severity**: Medium

### Statement
Test component interactions explicitly:

- **Integration Tests**: Verify components work together correctly
- **Boundary Testing**: Test at system boundaries (APIs, databases)
- **Realistic Data**: Use representative test data

### Action
Supplement unit tests with integration tests for critical paths.

### Rationale
Unit tests verify components work in isolation; integration tests verify they work together.
<!-- RULE END: TEST-INT-001 -->
