# SQL Authoring

## Purpose

This document defines **SQL authoring standards** to ensure queries are readable, auditable, and maintainable.

---

<!-- RULE START: DB-SQL-001 -->
## Rule DB-SQL-001: Named Bind Parameters

**Domain**: Database / SQL  
**Severity**: High

### Statement
Use named bind keys rather than positional `?` placeholders:

- Use actual keys for bind references (e.g., `:orderId`, `:customerId`)
- Inline the binds in an array literal so names map to variables in one place
- Exception: Long lists of literals in `IN` conditions may use positional binds

### Example
```php
$sql = "SELECT * FROM orders WHERE customer_id = :customerId AND status = :status";
$binds = [':customerId' => $customerId, ':status' => $status];
```

### Action
Favor `:namedBindKey` over `?` binds for clarity and maintainability.

### Rationale
Named binds are self-documenting and reduce errors when modifying queries with many parameters.
<!-- RULE END: DB-SQL-001 -->

---

<!-- RULE START: DB-SQL-002 -->
## Rule DB-SQL-002: Minimal String Fragmentation

**Domain**: Database / SQL  
**Severity**: Medium

### Statement
Define raw SQL using as few string literals as possible:

- No excessive concatenation of small strings
- Split SQL strings only when conditional logic requires it
- Keep multi-line SQL fully contained in a single assignment when possible

### Example
```php
// Good - single heredoc or multi-line string
$sql = <<<SQL
SELECT o.order_id, o.customer_id, c.name
FROM orders o
JOIN customers c ON c.id = o.customer_id
WHERE o.status = :status
SQL;

// Bad - fragmented concatenation
$sql = "SELECT o.order_id, o.customer_id, c.name " .
       "FROM orders o " .
       "JOIN customers c ON c.id = o.customer_id " .
       "WHERE o.status = :status";
```

### Action
Optimize SQL for readability and auditability first, then flexibility.

### Rationale
Fragmented SQL is harder to read, copy for debugging, and audit for security issues.
<!-- RULE END: DB-SQL-002 -->

---

<!-- RULE START: DB-SQL-003 -->
## Rule DB-SQL-003: Readable SQL Formatting

**Domain**: Database / SQL  
**Severity**: Medium

### Statement
Format SQL for vertical readability:

- Keep each `JOIN` on its own line (including its `ON` conditions)
- Prefer vertically aligned, readable SQL over dynamic assembly
- Keep SQL compact rather than dynamically assembled

### Example
```sql
SELECT 
    o.order_id,
    o.customer_id,
    c.name
FROM orders o
JOIN customers c ON c.id = o.customer_id
LEFT JOIN addresses a ON a.customer_id = c.id
WHERE o.status = :status
    AND o.created_at > :startDate
ORDER BY o.created_at DESC
```

### Action
Prioritize readability and auditability over clever dynamic construction.

### Rationale
Readable SQL is easier to review, debug, and maintain. Vertical formatting makes complex queries scannable.
<!-- RULE END: DB-SQL-003 -->
