# Agent Rails

Agent Rails is an open-source framework for safer AI-assisted software development.

It is based on a simple operating thesis:

```text
Good codebase
+ disciplined AI workflow
+ operational controls
= safer AI-assisted software development
```

Most AI coding adoption focuses on the coding agent itself. Agent Rails focuses on the engineering system around the agent: the structure of the codebase, the way humans guide AI work, and the controls that prevent risky changes from bypassing review.

## The Three Pillars and source code

| Pillar | Purpose | Supporting repository |
|---|---|---|
| Agent-Friendly Codebase | Make software easier for humans and AI agents to understand, modify, and verify. | [`AI_project_templates`](https://github.com/portero-aylagas/AI_project_templates) |
| Disciplined Agent Workflow | Guide AI coding work through scoped tasks, planning, small patches, verification, and review. | [`agent_skill_safe_project_improvement_system`](https://github.com/portero-aylagas/agent_skill_safe_project_improvement_system) |
| Operational Guardrails | Move mature AI-assisted work into a controlled issue-to-PR workflow with validation and human handoff. | [`agentic-loop-PR`](https://github.com/portero-aylagas/agentic-loop-PR) |

Each supporting repository contains its own implementation details and usage notes. This repository explains the umbrella system and the system-level business, compliance, risk, and deployment logic.

## Evidences of use
Project refactor: https://github.com/portero-aylagas/job_search_automation/tree/main/docs/refactor-reports
Agentic loop: https://github.com/portero-aylagas/agentic-loop-PR/issues/29 -> https://github.com/portero-aylagas/agentic-loop-PR/issues/29


## What Agent Rails Controls

| Area | Control objective |
|---|---|
| Codebase structure | Keep code, prompts, schemas, tests, configuration, and documentation understandable and verifiable. |
| Agent behavior | Prevent vague, broad, unreviewable AI coding sessions. |
| Change size | Prefer small, scoped improvements over large uncontrolled rewrites. |
| Verification | Use tests and repeatable commands as the agreement between human and AI. |
| Pull requests | Convert AI-assisted work into reviewable diffs. |
| Human accountability | Keep engineers responsible for approval, merge, and deployment decisions. |
| Automation maturity | Add automation only after the codebase and workflow are stable. |

## Recommended Use Pattern

1. **Start a new AI-ready codebase** with templates.
2. **Improve any existing repository** with a disciplined safe-refactor workflow.
3. **Add issue-to-PR automation** only when the repository and team workflow are mature enough.

## Repository Contents

| File | Purpose |
|---|---|
| [`use_case_definition.md`](./use_case_definition.md) | Defines the system-level use case, users, stakeholders, success criteria, and boundaries. |
| [`workflow_documentation.md`](./workflow_documentation.md) | Explains the simplified Agent Rails operating workflow. |
| [`workflow_evidence.md`](./workflow_evidence.md) | Links the repositories that implement the three pillars. |
| [`roi_risk_assessment.md`](./roi_risk_assessment.md) | Describes costs, ROI logic, assumptions, opportunities, and risks. |
| [`compliance/eu_ai_act_compliance.md`](./compliance/eu_ai_act_compliance.md) | First-pass EU AI Act assessment. |
| [`compliance/gdpr_documentation.md`](./compliance/gdpr_documentation.md) | First-pass GDPR and data protection review. |
| [`strategic_plan.md`](./strategic_plan.md) | Deployment, adoption, and commercialisation plan. |

## Positioning

Agent Rails is not another AI coding agent.

It is the control layer around AI coding agents.

The objective is not to replace developers. The objective is to make AI-assisted software development more structured, reviewable, testable, and governable.
