# Prompt Engineering for Cascade

## Purpose

This document provides **best practices for writing effective prompts** when working with Cascade AI.

---

## Request Specificity

- **Clear Intent**: State exactly what you want changed/created
- **Context**: Provide relevant context (file paths, function names, requirements)
- **Constraints**: Specify any limitations or requirements upfront

### Example
> "Refactor the `processOrder()` method in `OrderService.php` to use dependency injection instead of creating dependencies internally"

---

## Iterative Refinement

- **Start Small**: Begin with the core functionality
- **Validate Early**: Test/verify before adding complexity
- **Incremental Changes**: Make changes in small, verifiable steps
- **Action**: Break large tasks into smaller, sequential requests

---

## Project-Specific Adaptations

### Framework Awareness
- **Follow Framework Conventions**: Adhere to framework-specific best practices (e.g., Magento, Laravel, Symfony)
- **Use Framework Features**: Leverage built-in framework capabilities rather than reinventing
- **Plugin/Module System**: Use framework's extension mechanisms
- **Action**: Check framework documentation for recommended patterns

### Language-Specific
- **Modern Features**: Use current language version features appropriately
- **Type Safety**: Use type hints, return types, and strict typing where available
- **Standards**: Follow PSR standards for PHP, PEP for Python, etc.
- **Action**: Apply language-specific best practices automatically
