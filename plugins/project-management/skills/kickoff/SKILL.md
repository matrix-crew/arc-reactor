---
name: Kickoff
description: This skill should be used when the user asks to "start a new project", "kick off a project", "design a new app", "set up project architecture", "create a project spec", "plan a new service", or discusses building something new from scratch. Guides a structured process from discovery interview through spec generation.
---

# Kickoff

Guide a complete project kickoff through structured interviews and spec generation. The output is `specifications/kickoff.md` at the project root, along with bootstrapped project files.

## Process Overview

```
Discovery Interview → Technical Architecture → UI/UX Design → Risk Analysis → Spec Generation → Project Bootstrap
```

Conduct each phase as an interactive conversation. Ask questions one section at a time. Summarize findings at the end of each phase before proceeding. Allow skipping phases if information is already known.

## Phase 1: Discovery Interview

**1.1 Project Vision**
- What problem does this project solve?
- Who are the target users?
- What is the core value proposition?
- Are there existing solutions or competitors?

**1.2 Scope & Requirements**
- What are the must-have features for the first release (MVP)?
- What are nice-to-have features for later?
- Are there hard deadlines or milestones?
- What are the non-functional requirements (performance, availability, compliance)?

**1.3 Constraints**
- Team size and skill set?
- Budget or infrastructure constraints?
- Third-party integrations required?
- Regulatory or compliance requirements?

Summarize discovery findings before proceeding.

## Phase 2: Technical Architecture

**2.1 Technology Stack**
- Language, runtime, framework
- Database and caching
- Infrastructure and deployment
- Present recommendations with trade-offs and let the user decide

**2.2 System Architecture**
- High-level component diagram (text or ASCII)
- Service boundaries (monolith vs microservices)
- Data flow between components
- External service integrations

**2.3 Data Model**
- Core entities and relationships
- Key attributes per entity
- Database schema outline

**2.4 API Design**
- API style (REST, GraphQL, RPC)
- Key endpoints and operations
- Authentication and authorization strategy

## Phase 3: UI/UX Design

**3.1 User Flows**
- Primary user journeys (signup → onboarding → core action)
- Decision points and branching paths
- Success and error states

**3.2 Screen Inventory**
- All screens/pages needed
- Navigation structure
- Shared components and layouts

**3.3 Design System Decisions**
- Responsive strategy
- Component library choice
- Typography, color, spacing
- Accessibility requirements

**3.4 Interaction Patterns**
- Form handling and validation
- Loading and skeleton states
- Error handling and user feedback

## Phase 4: Risk & Concerns Analysis

**4.1 Technical Risks**
- Performance bottlenecks
- Scalability concerns
- Single points of failure

**4.2 Security Concerns**
- Authentication/authorization attack surfaces
- Data protection needs
- Input validation gaps

**4.3 Operational Risks**
- Deployment complexity
- Monitoring gaps
- Third-party dependency risks

**4.4 Mitigation Strategies**
- Concrete mitigation for each identified risk
- Prioritize by likelihood and impact

## Phase 5: Generate kickoff.md

Save the complete kickoff output as `specifications/kickoff.md`. Create the `specifications/` directory if it does not exist. The file should contain all findings from Phases 1-4 organized into sections:

```markdown
# Project Kickoff: <project-name>

## 1. Discovery
(Vision, scope, requirements, constraints)

## 2. Technical Architecture
(Stack, system design, data model, API design)

## 3. UI/UX Design
(User flows, screens, design system, interactions)

## 4. Risk Assessment
(Technical, security, operational risks and mitigations)

## 5. Next Steps
(Recommended immediate actions)
```

Never overwrite an existing `specifications/kickoff.md` without asking.

## Phase 6: Project Bootstrap

Generate essential project files at the root:

- **CLAUDE.md** - Project overview, tech stack, build/test commands, conventions
- **README.md** - Project description, features, tech stack, getting started, structure
- **.gitignore** - Appropriate entries for the chosen tech stack

## Key Principles

- Never skip the discovery interview; all design decisions depend on it
- Present trade-offs and let the user make decisions, do not assume
- Summarize each phase before moving to the next
- Never overwrite existing files without asking
- Keep spec documents concise but complete
