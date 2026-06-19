# Workflow Documentation — Agent Rails

Agent Rails is used progressively. The automation loop is not the starting point.

The recommended workflow is:

```text
Start with templates
→ improve with safe refactor workflow
→ add automation only when the repository is mature
```

## 1. Start a New AI-Ready Repository

Use:

https://github.com/portero-aylagas/AI_project_templates

Purpose:

- create an agent-friendly repository from the beginning;
- establish clear structure;
- separate prompts, schemas, provider logic, application logic, tests, and documentation;
- make verification commands explicit;
- give AI agents a clear map of where changes belong;
- reduce ambiguity before any AI coding work begins.

Simple rule:

> The repository should give the AI a map and a way to check its work.

This is the best starting point when the work begins from a blank or early-stage codebase.

## 2. Improve an Existing Repository Safely

Use:

https://github.com/portero-aylagas/agent_skill_safe_project_improvement_system

Purpose:

- inspect the repository before editing;
- characterize the current architecture;
- verify setup and available commands;
- identify improvement opportunities;
- make one scoped patch at a time;
- run verification;
- review the actual diff;
- avoid broad uncontrolled rewrites.

This applies to both:

- repositories originally created from the templates;
- normal existing repositories that were not designed for AI agents.

Typical use cases:

- small refactors;
- test cleanup;
- documentation improvement;
- structure improvements;
- reducing coupling;
- clarifying prompts or schemas;
- making verification easier;
- preparing the repository for later automation.

Simple rule:

> The AI should not just start coding. It needs a bounded task, a plan, verification, and review.

## 3. Add Automation When the Repository Is Mature

Use:

https://github.com/portero-aylagas/agentic-loop-PR

Purpose:

- automate the issue-to-PR loop;
- create or reuse a branch;
- run an agentic planning and implementation cycle;
- validate changes;
- open or update a pull request;
- stop for human review.

This should be considered only when:

- the repository structure is understandable;
- tests or verification commands exist;
- human review expectations are clear;
- sensitive files and protected paths are known;
- the team has already used scoped AI-assisted changes manually;
- the cost of automation is justified by repeated work.

Simple rule:

> The automation loop should be added after the codebase and human workflow are stable, not before.

## 4. Recommended Adoption Path

| Stage | Action | Main output |
|---|---|---|
| 1 | Use templates for new AI-ready repositories. | Clear structure and verification path. |
| 2 | Use the safe improvement workflow on existing repositories. | Small verified refactors and better agent-readiness. |
| 3 | Add the automation loop for mature repositories. | Reviewable issue-to-PR automation with human handoff. |

## 5. What the Workflow Demonstrates

Agent Rails demonstrates that safe AI-assisted development is not only a model capability problem.

It requires:

- an agent-friendly codebase;
- a disciplined way of working;
- operational guardrails around automation;
- human review before merge or deployment.

The result is a practical route from manual AI-assisted improvements to controlled automation.

## 6. Known Limitations

- The framework does not guarantee correct AI-generated code.
- It depends on the quality of tests and verification commands.
- It requires human review discipline.
- The automation loop is not suitable for immature or poorly structured repositories.
- Downstream users must define their own protected paths, secrets policy, and repository-specific safety rules.
- Use in regulated or safety-critical domains requires additional assessment.
