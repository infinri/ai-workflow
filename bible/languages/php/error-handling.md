# PHP Error Handling

## Purpose

This document defines **error handling principles** for PHP code to ensure robust, debuggable, and maintainable applications.

---

<!-- RULE START: PHP-ERR-001 -->
## Rule PHP-ERR-001: Fail Fast

**Domain**: PHP / Error Handling  
**Severity**: High

### Statement
Validate inputs early and throw meaningful exceptions:

- **Early Validation**: Check preconditions at the start of functions
- **Meaningful Messages**: Exception messages must describe what went wrong and why
- **Specific Exceptions**: Use or create specific exception types for different failure modes

### Action
Never suppress exceptions silently; always log or handle explicitly.

### Rationale
Silent failures mask bugs and make debugging extremely difficult. Early, explicit failures are easier to diagnose and fix.
<!-- RULE END: PHP-ERR-001 -->

---

<!-- RULE START: PHP-ERR-002 -->
## Rule PHP-ERR-002: Graceful Degradation

**Domain**: PHP / Error Handling  
**Severity**: Medium

### Statement
Handle errors appropriately for the context:

- **User-Facing**: Show friendly messages, log technical details
- **API**: Return structured error responses with appropriate HTTP codes
- **Background Jobs**: Log errors, implement retry logic where appropriate

### Action
Consider the error's audience and impact when designing error handling.

### Rationale
Different contexts require different error handling strategies. A stack trace shown to users is both a security risk and poor UX.
<!-- RULE END: PHP-ERR-002 -->
