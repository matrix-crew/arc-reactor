---
name: Planning
description: This skill should be used when the user asks to "plan this feature", "write a technical spec", "design the implementation for", "how should I architect this", "break this down into tasks", or has a specific feature in mind and needs a detailed implementation plan with technical spec, design decisions, and risk analysis.
---

# Planning

Produce a detailed implementation plan for a specific feature, covering technical specification, design decisions, task breakdown, and risk management.

## Process

### 1. Clarify Requirements

Before planning, ensure the feature is well-defined:
- What exactly should this feature do? (functional requirements)
- What are the constraints? (performance, compatibility, timeline)
- Who uses it and how? (user stories or scenarios)
- What does success look like? (acceptance criteria)

Ask clarifying questions if any of these are ambiguous.

### 2. Technical Specification

Define the technical approach:

**Architecture**
- How does this feature fit into the existing system?
- Which modules/files need to be created or modified?
- What are the data flow and state management implications?
- Are new database tables, API endpoints, or services needed?

**Interface Design**
- Public API surface (function signatures, endpoint contracts, component props)
- Input validation and error responses
- Data types and schemas

**Dependencies**
- New libraries or services required
- Existing code that must be understood or modified
- External API integrations

### 3. Design Decisions

Document key decisions with rationale:

```
### Decision: <title>

**Options considered:**
1. <Option A> - <pros/cons>
2. <Option B> - <pros/cons>

**Chosen:** Option <X>
**Rationale:** <why this option is best for the current context>
```

Cover decisions on:
- Algorithmic approach
- Data storage strategy
- UI component structure (if applicable)
- Error handling strategy
- Testing approach

### 4. Risk Analysis

Identify and plan for risks specific to this feature:

**Implementation Risks**
- Complex logic that is error-prone
- Tight coupling with existing code
- Migration or data transformation needs

**Integration Risks**
- Breaking changes to existing APIs or interfaces
- Backward compatibility concerns
- Third-party service reliability

**Performance Risks**
- Operations that may not scale (N+1 queries, unbounded lists)
- Memory or CPU-intensive operations
- Network latency impact

For each risk, provide:
- Likelihood (low / medium / high)
- Impact (low / medium / high)
- Mitigation strategy

### 5. Task Breakdown

Break the implementation into ordered, concrete tasks:

```
## Implementation Plan

### Phase 1: Foundation
- [ ] Task 1: <description> (simple)
      Files: <specific file paths>
- [ ] Task 2: <description> (medium)
      Files: <paths>
      Depends on: Task 1

### Phase 2: Core Logic
- [ ] Task 3: <description> (complex)
      Files: <paths>
      Risks: <reference to risk section>

### Phase 3: Testing & Polish
- [ ] Task 4: Write unit tests for <module>
- [ ] Task 5: Write integration tests for <flow>
- [ ] Task 6: Update documentation
```

Each task should include:
- Clear deliverable
- Specific files to create or modify
- Complexity estimate (simple / medium / complex)
- Dependencies on other tasks

### 6. Save to Spec

Save the complete plan to the `specifications/` directory at the project root. Create the directory if it does not exist. Use a descriptive filename based on the feature:

```
specifications/
├── auth-system.md
├── payment-integration.md
└── ...
```

Each file should be a standalone document containing the full technical spec, design decisions, risk analysis, and task breakdown. Never overwrite existing files without asking.

### 7. Confirm and Proceed

Present the complete plan and ask for approval. Offer to:
- Adjust scope or approach based on feedback
- Start implementing immediately

## Key Principles

- Be specific: reference actual file paths, function names, and line numbers
- Every design decision needs a rationale, not just a conclusion
- Risks without mitigations are incomplete
- Tasks should be small enough to complete in a single session
- The plan should be executable by someone unfamiliar with the codebase
