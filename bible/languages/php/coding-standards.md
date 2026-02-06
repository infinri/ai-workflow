# PHP Coding Standards

## Purpose

This document defines **PHP-specific coding standards** for consistent, maintainable code.

---

<!-- RULE START: PHP-TYPE-001 -->
## Rule PHP-TYPE-001: DocBlock for Non-Obvious Types

**Domain**: PHP / Coding Standards  
**Severity**: Low

### Statement
When a variable's type isn't obvious from how it was obtained, add a docblock annotation:

```php
/** @var OrderInterface $order */
$order = $this->orderRepository->getById($orderId);
```

### Action
Add `/** @var <type> <variable> */` before variable definitions when the type isn't clear from context.

### Rationale
Helps IDE autocompletion and makes code self-documenting without adding runtime type checks.
<!-- RULE END: PHP-TYPE-001 -->

---

<!-- RULE START: PHP-ERR-002 -->
## Rule PHP-ERR-002: Try-Catch Standards

**Domain**: PHP / Error Handling  
**Severity**: High

### Statement
When using try-catch blocks:

- Always catch `\Throwable` (not just `\Exception`)
- Always log the error message

### Example
```php
try {
    $this->processOrder($order);
} catch (\Throwable $e) {
    $this->logger->error($e->getMessage(), ['exception' => $e]);
    throw $e;
}
```

### Action
Never swallow exceptions silently. Always log before re-throwing or handling.

### Rationale
`\Throwable` catches both exceptions and errors. Logging ensures issues are traceable in production.
<!-- RULE END: PHP-ERR-002 -->
