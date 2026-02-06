# Performance & Profiling

## Purpose

This document defines **performance principles and optimization guidelines** for maintaining efficient, scalable code.

---

<!-- RULE START: PERF-BIGO-001 -->
## Rule PERF-BIGO-001: Algorithm Complexity Awareness

**Domain**: Performance  
**Severity**: High

### Statement
All code must consider time and space complexity:

- **O(1)** - Constant: Hash lookups, array access
- **O(log n)** - Logarithmic: Binary search
- **O(n)** - Linear: Single loop iterations
- **O(n log n)** - Linearithmic: Efficient sorting
- **Avoid O(n²) or worse** unless dataset is guaranteed small

### Action
Before implementing loops, consider if there's a more efficient approach.

### Rationale
Poor algorithm choice can cause exponential performance degradation as data grows. A seemingly simple nested loop can bring production systems to a halt.
<!-- RULE END: PERF-BIGO-001 -->

---

<!-- RULE START: PERF-OPT-001 -->
## Rule PERF-OPT-001: Optimization Order

**Domain**: Performance  
**Severity**: Medium

### Statement
Follow this optimization order:

1. **Make it work** - Correct functionality first
2. **Make it right** - Clean, maintainable code
3. **Make it fast** - Optimize only when measured

### Action
Profile before optimizing; measure, don't assume.

### Rationale
Premature optimization leads to complex, hard-to-maintain code. Optimization without measurement often targets the wrong bottlenecks.
<!-- RULE END: PERF-OPT-001 -->

---

<!-- RULE START: PERF-LAZY-001 -->
## Rule PERF-LAZY-001: Lazy Loading

**Domain**: Performance  
**Severity**: Medium

### Statement
Load resources only when needed:

- **Lazy Loading**: Defer loading until first access
- **Caching**: Cache expensive computations and frequently accessed data
- **Database Queries**: Minimize N+1 queries, use eager loading when appropriate

### Action
Evaluate whether data is needed immediately or can be deferred.

### Rationale
Eager loading of unused resources wastes memory and CPU cycles. Lazy loading improves startup time and reduces unnecessary work.
<!-- RULE END: PERF-LAZY-001 -->
