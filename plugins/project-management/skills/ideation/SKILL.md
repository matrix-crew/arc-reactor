---
name: Ideation
description: This skill should be used when the user asks to "suggest features", "what should I build next", "what's missing in this project", "analyze competitors", "find improvement opportunities", or wants ideas for new features, enhancements, or improvements to an existing project.
---

# Ideation

Research and analyze an existing project to surface actionable feature ideas, improvement opportunities, and strategic insights.

## Process

### 1. Understand the Project

Analyze the current codebase to build context:
- Read CLAUDE.md, README.md, and package manifests to understand purpose and stack
- Scan the project structure to identify existing features and modules
- Check recent git history to understand development momentum and focus areas
- Identify the target user base and use cases from documentation

### 2. Gap Analysis

Identify what the project is missing relative to its goals:
- **Feature gaps**: Core functionality that users would expect but is absent
- **Quality gaps**: Missing error handling, validation, logging, or monitoring
- **Developer experience gaps**: Missing tooling, documentation, or testing infrastructure
- **Accessibility gaps**: i18n, a11y, responsive design, or performance concerns

### 3. Competitive Research

If the project has known competitors or similar tools:
- Search for comparable projects and their feature sets
- Identify differentiating features the project could adopt
- Note industry trends and emerging patterns relevant to this domain
- Highlight features that competitors have that this project lacks

### 4. Technical Opportunities

Identify improvements based on the codebase itself:
- Code patterns that could benefit from refactoring or abstraction
- Performance optimization opportunities (caching, lazy loading, indexing)
- Security hardening areas
- Infrastructure improvements (CI/CD, monitoring, deployment)

### 5. Present Ideas

Organize findings into a prioritized list:

```
## Feature Ideas

### High Impact / Low Effort
1. **<Feature name>** - <description>
   Why: <user value or business rationale>
   Effort: ~<estimate>

### High Impact / High Effort
2. **<Feature name>** - <description>
   Why: <rationale>
   Effort: ~<estimate>

### Quick Wins
3. **<Feature name>** - <description>

### Strategic / Long-term
4. **<Feature name>** - <description>
```

For each idea, include:
- What it does and why it matters
- Which users benefit
- Rough effort estimate (small / medium / large)
- Dependencies or prerequisites

### 6. Save Results

Save the ideation output to the `ideations/` directory at the project root. Create the directory if it does not exist. Use a descriptive filename with the date:

```
ideations/
├── 2025-01-15-feature-ideas.md
├── 2025-02-03-competitive-analysis.md
└── ...
```

Each file should be a standalone document containing the full analysis and prioritized ideas. Never overwrite existing files.

### 7. Discuss and Refine

Present the ideas and ask the user which ones resonate. Offer to elaborate on any specific idea or pivot based on feedback. Update the saved file with any refinements.

## Key Principles

- Ground ideas in what the codebase actually needs, not generic suggestions
- Prioritize by impact-to-effort ratio
- Consider the project's current stage (MVP, growth, mature)
- Back up suggestions with evidence from the codebase or competitive research
