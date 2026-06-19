# Use Case Definition — Agent Rails

## 1. Business Problem Statement

AI coding agents can generate code quickly, but many teams use them without enough structure, workflow discipline, or operational control.

This creates predictable software delivery risks:

- changes are too large to review properly;
- the agent edits the wrong files;
- prompts, business logic, model calls, and tests become mixed together;
- verification commands are unclear or missing;
- generated pull requests lack traceability;
- developers overtrust AI-generated changes;
- sensitive files, secrets, or private data may be exposed;
- teams cannot explain why a change was made or how it was verified.

The problem is not only the AI model. The surrounding software engineering system is often not ready for AI-assisted development.

## 2. Target Users

Agent Rails is designed for:

- software developers using AI coding agents;
- AI engineers building LLM-enabled software;
- maintainers of open-source repositories;
- startups and small engineering teams;
- software agencies delivering client repositories;
- engineering managers evaluating AI-assisted development workflows;
- security and compliance reviewers responsible for safe software delivery.

## 3. Current Operational State

Many teams already use AI coding assistants, but usage is often informal:

- task descriptions are vague;
- repositories are not structured for agent navigation;
- tests are incomplete or hard to run;
- AI-generated diffs are too broad;
- human review is inconsistent;
- automation is added before the repository is ready;
- operational limits are not explicit.

This makes productivity gains inconsistent and increases the risk of hidden technical debt.

## 4. Proposed AI Solution

Agent Rails provides a structured operating model for AI-assisted software development.

It combines three pillars:

| Pillar | Function |
|---|---|
| Agent-Friendly Codebase | Structure software so humans and AI agents can understand, change, and verify it. |
| Disciplined Agent Workflow | Guide agent work through scoped tasks, planning, small patches, tests, and diff review. |
| Operational Guardrails | Use issue-to-PR automation, validation, protected boundaries, and human handoff when the repository is mature. |

The system is implemented as an umbrella framework linking three existing repositories:

| Pillar | Repository |
|---|---|
| Agent-Friendly Codebase | https://github.com/portero-aylagas/AI_project_templates |
| Disciplined Agent Workflow | https://github.com/portero-aylagas/agent_skill_safe_project_improvement_system |
| Operational Guardrails | https://github.com/portero-aylagas/agentic-loop-PR |

## 5. Type of AI System

Agent Rails is best described as:

- generative AI-assisted software development support;
- human-in-the-loop engineering workflow;
- software change management support;
- AI coding governance and operational control framework;
- developer productivity and quality-assurance support.

It is not positioned as a fully autonomous developer, production deployment agent, hiring system, credit system, healthcare system, legal decision system, or safety-critical controller.

## 6. Key Stakeholders

| Stakeholder | Interest |
|---|---|
| Developers | Use AI assistance without losing control over architecture, tests, or code quality. |
| Reviewers / maintainers | Receive smaller, more understandable, better verified changes. |
| Engineering managers | Improve productivity without creating unmanaged technical risk. |
| Security reviewers | Reduce secret exposure, unsafe changes, and untracked automation. |
| End users | Benefit from more reliable software with fewer unsafe AI-generated defects. |
| Open-source contributors | Follow a clear contribution process when AI tools are used. |
| AI model providers | Provide upstream model capability without owning downstream software delivery decisions. |

## 7. Success Criteria

Agent Rails is successful if it can show measurable improvement in safe AI-assisted development.

| Success criterion | Example measurement |
|---|---|
| Faster setup of AI-ready repositories | Hours saved when starting a new AI-enabled codebase. |
| More reviewable AI-assisted changes | Percentage of AI-assisted changes kept under an agreed diff size or file count. |
| Better verification discipline | Percentage of AI-assisted changes with tests or documented verification commands. |
| Lower unsafe-change rate | Number of AI changes blocked due to wrong files, missing tests, or protected paths. |
| Reduced rework | Review cycles or defect fixes avoided after using scoped workflows. |
| Better auditability | Issues, plans, diffs, verification output, and PR review evidence are linked. |

## 8. Out-of-Scope Boundaries

Agent Rails does not aim to:

- automatically merge code;
- automatically deploy to production;
- replace human responsibility for software correctness;
- process secrets or private customer data inside prompts;
- bypass repository access controls;
- make legal, hiring, financial, healthcare, education-access, or public-service decisions;
- guarantee that AI-generated code is correct;
- certify compliance for downstream users in every deployment context.

## 9. Core Positioning

Agent Rails is not another AI coding agent.

It is a control layer around AI coding agents.

Its value is moving from ad hoc AI-generated code toward a repeatable, reviewable, and governed software delivery process.
