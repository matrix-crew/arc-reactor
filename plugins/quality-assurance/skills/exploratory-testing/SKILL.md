---
name: exploratory-testing
description: This skill should be used when the user asks to "explore this code for bugs", "find edge cases", "what could go wrong", "test this thoroughly", or when the user wants a comprehensive analysis of potential failure points in code.
---

# Exploratory Testing

Perform systematic exploratory testing by analyzing code paths, identifying potential failure points, and testing unexpected scenarios that automated tests might miss.

## Exploratory Testing Process

### 1. Identify Target

Determine the scope of exploration:
- A specific file or module
- A feature or user flow (trace across multiple files)
- A recent change (check git diff for context)

### 2. Map the Feature

Build a mental model of the code:
- Trace execution from entry point to output
- Identify all dependencies (APIs, databases, external services)
- Find configuration values and feature flags
- Map state transitions and data flow

### 3. Identify Risk Areas

Systematically check for high-risk patterns:

**Input Boundaries:**
- Empty, null, undefined inputs
- Very large inputs (strings, arrays, numbers)
- Special characters, unicode, emoji
- Negative numbers, zero, MAX_INT

**Concurrency & State:**
- Race conditions in shared state
- Out-of-order operations
- Partial failures during multi-step processes
- Stale cache or stale state

**Error Handling:**
- What happens when dependencies fail?
- Network timeouts, connection refused
- Invalid responses from external APIs
- Disk full, permission denied

**Security:**
- Input validation gaps (SQL injection, XSS, command injection)
- Authentication/authorization bypass paths
- Sensitive data exposure in logs or errors
- CSRF, SSRF vulnerabilities

**Data Integrity:**
- Partial writes during failures
- Missing rollback on error
- Inconsistent state between related records
- Timezone, locale, encoding issues

### 4. Create Test Charter

Generate a structured list of scenarios to investigate:

```
## Exploratory Test Charter: <feature>

### Scenario 1: Boundary Input Testing
- [ ] Input with 255+ characters
- [ ] Unicode and emoji in text fields
- [ ] All fields empty

### Scenario 2: Error Recovery
- [ ] Service unavailable during operation
- [ ] Timeout during external API call
- [ ] Duplicate request handling

### Scenario 3: Security
- [ ] Injection attempts in input fields
- [ ] Authorization check bypass paths
```

### 5. Execute and Report

Test each scenario and document findings:

```
## Exploratory Testing Report

### Summary
- Tested: X scenarios
- Passed: Y | Failed: Z | Unexpected: W

### Bugs Found
1. [HIGH] Description (file:line)
2. [MEDIUM] Description (file:line)

### Observations
- Notable behaviors that aren't bugs but could be improved

### Recommendations
- Suggested fixes with priority
- Suggested automated tests to prevent regression
```

### 6. Suggest Regression Tests

For each bug found, offer to create automated tests that would catch the issue if it recurs.

## Key Principles

- **Think adversarially**: Try to break things, not confirm they work
- **Document everything**: Record both failures and interesting passing behavior
- **Prioritize by impact**: Focus on security and data integrity first
- **Be systematic**: Follow the charter, don't just randomly test
- **Suggest prevention**: Every bug found should lead to a regression test recommendation
