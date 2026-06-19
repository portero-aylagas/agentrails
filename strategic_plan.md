# Strategic Plan — Agent Rails

## 1. Strategic Positioning

Agent Rails is an open-source framework for safer AI-assisted software development.

It is positioned as the control layer around AI coding agents, not as another AI coding agent.

The strategic thesis is:

```text
Agent-friendly codebase
+ disciplined AI workflow
+ operational guardrails
= safer AI-assisted software development
```

The market problem is that many teams adopt AI coding agents before their repositories, workflows, and review controls are ready. Agent Rails gives teams a staged path from structured codebase setup to safe refactoring and, only later, automation.

## 2. Target Users

| Segment | Need |
|---|---|
| Solo developers | A repeatable way to structure and improve AI-enabled repositories. |
| Small software teams | Safer AI-assisted refactoring and review practices. |
| AI engineers | Clear separation of prompts, schemas, provider logic, tests, and application code. |
| Open-source maintainers | Transparent rules for accepting AI-assisted contributions. |
| Software agencies | A reusable delivery process for client repositories. |
| Engineering managers | A governed path for AI coding adoption without uncontrolled automation. |
| Security/compliance reviewers | Evidence of review, verification, and human accountability. |

## 3. Deployment Phases

| Phase | Focus | Description | Output |
|---|---|---|---|
| Phase 1 | Agent-friendly setup | Use templates to start new AI-ready repositories. | Structured codebase with clear prompts, schemas, tests, docs, and provider boundaries. |
| Phase 2 | Safe improvement workflow | Use the safe repository skill to improve existing repositories through small verified refactors. | Better structure, clearer tests, safer AI-assisted patches. |
| Phase 3 | Operational automation | Add issue-to-PR automation only when the repository and workflow are mature. | Controlled branch, validation, PR creation, and human handoff. |
| Phase 4 | Team adoption | Package the operating model for teams, agencies, and maintainers. | Repeatable onboarding, metrics, and governance templates. |

## 4. Timeline

| Phase | Timing | Milestones |
|---|---|---|
| Phase 1: Framework validation | Weeks 1-2 | Confirm repository structure, pillar mapping, usage documentation. |
| Phase 2: Controlled adoption | Weeks 3-6 | Apply safe refactor workflow to selected repositories and measure review burden. |
| Phase 3: Automation readiness | Weeks 7-10 | Decide whether selected repositories meet criteria for issue-to-PR automation. |
| Phase 4: Broader rollout | Weeks 11-16 | Package onboarding, examples, commercial offer, and metrics. |

Automation should not be treated as the default first step. It should be enabled only where repository maturity, tests, review owners, and protected paths are already in place.

## 5. Go-to-Market Strategy

Agent Rails should start as an open-source framework and grow through practical adoption evidence.

| Channel | Use |
|---|---|
| GitHub repository | Main distribution and documentation hub. |
| Technical articles | Explain the three-pillar model and common AI coding risks. |
| Developer demos | Show template setup, safe refactors, and later issue-to-PR automation. |
| Open-source examples | Show safe public usage without exposing secrets or private data. |
| Consulting outreach | Offer repository assessment and implementation support. |
| Engineering communities | Reach developers already using AI coding agents. |

## 6. Commercialisation Model

Recommended model:

```text
Open-source core + paid support, implementation, repository assessment, workflow integration, and governance templates.
```

Possible paid offers:

| Offer | Buyer | Value |
|---|---|---|
| Repository readiness assessment | Engineering managers, agencies | Identify gaps before using AI agents heavily. |
| Agent-friendly repository setup | Startups, AI teams | Build or refactor codebases for safer AI-assisted work. |
| Safe workflow implementation | Software teams | Add scoped task, verification, and review discipline. |
| Automation integration | Mature teams | Add issue-to-PR automation where justified. |
| Governance templates | Security/compliance teams | Define protected paths, AI usage rules, and review evidence. |
| Team enablement | Engineering teams | Train developers to use AI agents without bypassing normal engineering controls. |

## 7. Key Differentiator

Most AI coding products focus on the agent.

Agent Rails focuses on the environment around the agent:

- repository structure;
- human workflow discipline;
- verification;
- reviewability;
- operational controls;
- automation maturity.

The differentiator is not faster code generation alone. It is safer, repeatable, and reviewable AI-assisted software delivery.

## 8. Stakeholder Communication Plan

| Stakeholder | What they need to know | Communication method | Timing |
|---|---|---|---|
| Developers | How to use templates, safe refactors, and automation criteria. | README, examples, walkthroughs. | Before adoption and during first workflows. |
| Reviewers / maintainers | What evidence to expect in AI-assisted changes. | PR checklist, review notes. | During each AI-assisted change. |
| Engineering managers | ROI logic, risks, maturity gates, and adoption metrics. | Adoption report and KPI dashboard. | Weekly during pilot adoption. |
| Security reviewers | Secret rules, protected paths, provider data flows. | Security checklist and architecture notes. | Before automation is enabled. |
| Open-source contributors | How AI-assisted contributions should be disclosed and reviewed. | Contribution guidance in repository docs. | Before accepting external contributions. |
| Commercial clients | Boundaries, responsibilities, data handling, and support model. | Statement of work and data-flow documentation. | Before implementation. |

## 9. KPIs

| Phase | KPI | Target signal |
|---|---|---|
| Agent-friendly setup | Time to create usable AI-ready repository | Reduced setup time versus manual baseline. |
| Agent-friendly setup | Presence of tests, prompts, schemas, docs, provider boundaries | All required areas present. |
| Safe improvement workflow | Average size of AI-assisted diff | Small enough for normal review. |
| Safe improvement workflow | Percentage of AI-assisted changes with verification evidence | High and increasing. |
| Safe improvement workflow | Review rejection or rework rate | Stable or decreasing. |
| Automation readiness | Repositories passing maturity gate | Only mature repositories proceed. |
| Automation loop | PRs created with plan, verification, and human handoff | Consistent evidence trail. |
| Commercial adoption | Paid assessments or implementation engagements | Validates demand beyond open-source interest. |

## 10. Risks to Strategy

| Risk | Strategic impact | Response |
|---|---|---|
| Market sees Agent Rails as documentation only | Low perceived value | Show concrete workflow examples and measurable before/after metrics. |
| Automation receives too much attention | Users skip foundational steps | Position automation as the last stage, not the starting point. |
| Existing AI coding tools add similar guardrails | Differentiation pressure | Focus on open, tool-agnostic operating model and repository readiness. |
| Teams resist process overhead | Low adoption | Keep workflow lightweight and evidence-based. |
| Open-source adoption does not convert commercially | Weak business case | Offer services around implementation, assessment, and governance. |

## 11. Next Steps

1. Publish the umbrella repository with clear pillar mapping.
2. Keep repository-specific details inside the three linked repositories.
3. Use the templates for new AI-ready repositories.
4. Apply the safe improvement workflow to normal existing repositories.
5. Measure time saved, review burden, and rework.
6. Add issue-to-PR automation only after maturity criteria are met.
7. Package commercial services around repository assessment, workflow setup, and governance.

## 12. Strategic Conclusion

Agent Rails should remain open source at the core.

The commercial opportunity is not selling another coding agent. The opportunity is helping teams adopt AI coding agents safely through structure, workflow discipline, and operational controls.
