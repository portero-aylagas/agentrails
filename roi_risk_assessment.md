# ROI and Risk Assessment — Agent Rails

## 1. Cost Analysis

This analysis covers Agent Rails as an open-source framework adopted by a small software team that wants to use AI coding agents with stronger structure, workflow discipline, and operational controls.

The economic case should not be justified by cheap model calls alone. The case depends on whether Agent Rails reduces expensive engineering time, review friction, unsafe AI-generated changes, and repeated setup work.

## 2. Adoption Scenario

Base scenario:

| Input | Value |
|---|---:|
| Team size | 5 developers |
| Loaded engineering cost | 80 €/hour |
| AI-assisted improvement cycles | 160/year |
| Average time saved per cycle | 1.0 hour |
| New or reorganized AI-ready repositories | 4/year |
| Setup time saved per repository | 12 hours |
| Rework avoided through safer workflow | 30 hours/year |

Base output:

| Driver | Evidence label | Annual value |
|---|---|---:|
| Time saved on improvement cycles | `model_assumption` | 12,800 € |
| Faster AI-ready repository setup | `model_assumption` | 3,840 € |
| Avoided rework from safer AI usage | `model_assumption` | 2,400 € |
| Total annual gross benefit | Mixed | 19,040 € |

Important caveat: these are planning estimates. Real adoption should measure actual cycle time, review burden, rejected changes, and rework before using the model for a larger rollout decision.

## 3. Cost Estimate

| Cost area | Low | Base | High | Notes |
|---|---:|---:|---:|---|
| Repository assessment and cleanup | 1,500 € | 3,000 € | 6,000 € | Making one or more repositories agent-friendly. |
| Workflow setup | 1,000 € | 2,000 € | 4,000 € | Defining safe task rules, verification commands, and review expectations. |
| Template adaptation | 800 € | 1,500 € | 3,000 € | Adapting templates to team conventions. |
| Automation loop setup | 0 € | 1,500 € | 4,000 € | Only for mature repositories; skipped in low case. |
| Developer onboarding | 800 € | 1,600 € | 3,000 € | Training, examples, and review process. |
| Tool/API/CI cost | 300 € | 1,000 € | 2,000 € | Model usage, CI minutes, automation runtime. |
| Contingency | 600 € | 1,000 € | 2,000 € | Cleanup, iteration, and support buffer. |
| Total upfront cost | 5,000 € | 11,600 € | 24,000 € | Initial implementation and adoption work. |

Ongoing annual cost:

| Cost area | Low | Base | High | Notes |
|---|---:|---:|---:|---|
| Maintenance of templates and workflow docs | 800 € | 1,600 € | 3,000 € | Keeping rules and examples current. |
| Automation maintenance | 0 € | 1,000 € | 3,000 € | Only applies where automation loop is used. |
| Tool/API/CI usage | 600 € | 1,500 € | 4,000 € | Depends on number of agent runs and CI checks. |
| Review/process overhead | 1,000 € | 2,000 € | 5,000 € | Human review remains required. |
| Total ongoing annual cost | 2,400 € | 6,100 € | 15,000 € | Recurring operating cost. |

## 4. ROI Logic

Formula:

```text
ROI = (Net Benefit / Total Cost) × 100
```

Where:

```text
Net Benefit = Gross Benefit - Total Cost
```

The base case should be read as a controlled adoption scenario, not proof of universal ROI.

## 5. 12-Month ROI Scenario

| Item | Base case |
|---|---:|
| Gross benefit | 19,040 € |
| Upfront cost | 11,600 € |
| Ongoing annual cost | 6,100 € |
| Total 12-month cost | 17,700 € |
| Net benefit | 1,340 € |
| 12-month ROI | 7.6% |

Interpretation: the first year is mainly an adoption and validation year. The base case is only modestly positive because setup costs are paid early.

## 6. 36-Month ROI Scenario

| Item | Base case |
|---|---:|
| Gross benefit over 36 months | 57,120 € |
| Upfront cost | 11,600 € |
| Ongoing cost over 36 months | 18,300 € |
| Total 36-month cost | 29,900 € |
| Net benefit | 27,220 € |
| 36-month ROI | 91.0% |

Interpretation: the case improves if the framework becomes reusable and the setup cost is not repeated for every repository.

## 7. Break-Even Point

Base monthly gross benefit:

```text
19,040 € / 12 = 1,586.67 €/month
```

Base monthly ongoing cost:

```text
6,100 € / 12 = 508.33 €/month
```

Monthly net benefit after setup:

```text
1,586.67 € - 508.33 € = 1,078.34 €/month
```

Break-even estimate:

```text
11,600 € / 1,078.34 € = 10.8 months
```

Base-case break-even point: approximately **11 months**.

## 8. Assumptions Table

| Assumption | Value | Justification | Validation method |
|---|---:|---|---|
| Loaded developer cost | 80 €/hour | Planning value for a small professional software team. | Replace with actual internal rate. |
| Improvement cycles | 160/year | About 13 scoped AI-assisted improvements per month. | Count issues/PRs over pilot period. |
| Time saved per cycle | 1 hour | Conservative estimate for planning, patching, and initial implementation assistance. | Measure before/after cycle time. |
| Repository setup savings | 12 hours/repository | Templates reduce repeated setup and decision work. | Track setup time for new repositories. |
| Rework avoided | 30 hours/year | Safer workflow should reduce broad, failed, or hard-to-review AI changes. | Track rejected PRs and rework reasons. |
| Ongoing maintenance | 6,100 €/year | Documentation, review overhead, automation upkeep, and tool usage. | Track monthly operating cost. |

## 9. Timeline Estimate

### Adoption Timeline

| Phase | Timing | Output |
|---|---|---|
| Discovery and baseline | Weeks 1-2 | Repository map, current AI usage patterns, review pain points, verification commands, risk boundaries. |
| Template and workflow setup | Weeks 2-4 | Agent-friendly structure, safe workflow instructions, initial examples. |
| Controlled usage | Weeks 5-8 | Scoped improvements using safe workflow; measured cycle time and review burden. |
| Automation decision | Weeks 8-10 | Go/no-go decision on issue-to-PR automation for mature repositories. |
| Stabilization | Weeks 10-12 | Improved documentation, refined controls, measured adoption report. |

### Measurement Timeline

| Measurement | Baseline | During adoption | Evaluation |
|---|---|---|---|
| Time per improvement cycle | Week 1 | Weekly | Before/after comparison. |
| PR review burden | Week 1 | Per PR | Average review time and rejection reasons. |
| Verification coverage | Week 1 | Per change | Percentage of changes with test or verification evidence. |
| Rework | Week 1 | Weekly | Defects, reversions, and rejected changes. |
| Developer trust | Week 1 | Pulse checks | Adoption readiness and friction. |
| Automation readiness | Week 4 | Weekly | Whether repositories are mature enough for issue-to-PR automation. |

### Timeline Risks

- baseline measurement is skipped or incomplete;
- repositories require cleanup before agent workflows are useful;
- tests are too slow, flaky, or missing;
- developers resist structured workflow discipline;
- review burden remains high;
- automation is added before the repository is mature;
- sensitive files and protected paths are not defined;
- productivity gains are double-counted across setup, review, and rework categories.

## 10. Opportunity Map

| Opportunity | Business value | Evidence needed in adoption period |
|---|---|---|
| Faster AI-ready repository setup | Reduces repeated architectural and setup decisions. | Time to create a working repository with tests, prompts, schemas, and provider boundaries. |
| Safer frequent refactors | Turns ad hoc AI editing into small verified changes. | Number of successful scoped patches and review outcomes. |
| Better PR reviewability | Reduces large, unclear, hard-to-review AI diffs. | Diff size, file count, reviewer comments, rejection rate. |
| Reduced rework | Avoids wrong-file changes, hallucinated implementations, and unverified patches. | Rework hours, reverted changes, defect reports. |
| Higher automation readiness | Creates a path from manual AI-assisted work to controlled issue-to-PR automation. | Number of repositories meeting automation criteria. |
| Reusable operating model | Supports open-source maintainers, agencies, and small teams. | Repeatable setup across different repositories. |

## 11. Risk Map

| Risk | Why it matters | Mitigation |
|---|---|---|
| Time-saving overclaim | AI coding gains are easy to exaggerate if setup, review, and rework are ignored. | Measure before/after cycle time and review burden. |
| Double counting | Setup savings, refactor savings, and rework savings may overlap. | Separate metrics and de-duplicate benefit categories. |
| AI modifies wrong files | Wrong-file edits create hidden architectural damage. | Use scoped tasks, repository maps, protected paths, and diff review. |
| Low-quality generated changes | Generated code may compile but still be poorly designed. | Require tests, human review, and small patch size. |
| Review burden too high | Productivity gains disappear if every change needs heavy cleanup. | Measure review minutes and rejection reasons. |
| Secrets exposed | Issues, prompts, logs, or examples may contain API keys or credentials. | Use `.env.example`, secret scanning, prompt hygiene, and redaction. |
| Personal data in issues or prompts | Public repositories and AI providers may receive personal data unintentionally. | Minimize data, avoid real user examples, document provider transfers. |
| Team adoption failure | Developers may reject the process if it feels bureaucratic. | Keep rules lightweight and show measurable review improvements. |
| Automation added too early | Issue-to-PR automation can amplify weak structure and poor tests. | Require maturity criteria before automation. |
| Unclear accountability | Teams may blame the AI instead of owning review and merge decisions. | State that human maintainers remain accountable for approval and merge. |

## 12. Risk Assessment Matrix

Scoring scale:

- Likelihood: 1 = very unlikely, 5 = very likely
- Impact: 1 = negligible, 5 = severe
- Risk level = Likelihood × Impact

| Risk | Category | Likelihood | Impact | Risk level | Mitigation |
|---|---|---:|---:|---:|---|
| AI modifies wrong files | Technical / operational | 3 | 4 | 12 | Scoped tasks, protected paths, diff review. |
| AI introduces insecure code | Technical / security | 3 | 5 | 15 | Tests, review, security checks, dependency scanning. |
| Secrets exposed in prompts/logs | Security / GDPR | 2 | 5 | 10 | Secret scanning, redaction, `.env.example`, prompt rules. |
| Personal data appears in public issues | GDPR / operational | 3 | 4 | 12 | Contribution guidance, redaction, issue hygiene. |
| Developers overtrust AI output | Operational | 4 | 4 | 16 | Human approval gate, review checklist, explicit accountability. |
| Automation used before maturity | Operational / technical | 3 | 4 | 12 | Maturity gate before issue-to-PR loop. |
| Poor adoption | Operational | 3 | 3 | 9 | Keep workflow lightweight and measurable. |
| Unclear liability for AI-generated changes | Legal / operational | 3 | 4 | 12 | Human maintainer approval and documented review responsibility. |

## 13. Hype Versus Evidence

Evidence-backed claims:

- Structured repositories are easier to review, test, and maintain.
- Small scoped changes are easier to verify than broad rewrites.
- Human review remains necessary for AI-generated code.
- Automation is safer when tests, protected boundaries, and review gates already exist.

Uncertain claims:

- Agent Rails will save a fixed percentage of developer time in every repository.
- Issue-to-PR automation will be useful for immature repositories.
- AI-generated patches will consistently reduce review burden.
- Templates alone will make a repository ready for automation.

## 14. Adoption Readiness

Scoring scale: 1 = weak readiness, 5 = strong readiness.

| Factor | Score | Rationale | Adoption action |
|---|---:|---|---|
| Business pain clarity | 4 | AI coding adoption is common, but safe operating patterns are often weak. | Identify current review and rework pain. |
| Measurement clarity | 4 | Cycle time, review burden, and rework can be measured. | Track before/after metrics. |
| Technical readiness | 3 | Some repositories lack tests and structure. | Start with templates and safe refactors. |
| Governance readiness | 3 | Human review is clear, but secrets and data rules must be explicit. | Add protected paths and prompt hygiene. |
| Automation readiness | 2 | Automation should not be first. | Gate automation behind maturity criteria. |

Overall readiness: medium. The opportunity is credible, but automation should wait until repository structure and human workflow discipline are proven.

## 15. Investment Position

Recommended posture: start with a small adoption pilot.

Continue only if measured evidence shows:

- reduced time per scoped improvement;
- review burden does not increase materially;
- changes remain small and understandable;
- verification evidence is present for most AI-assisted changes;
- no unresolved secret, privacy, or trust incidents;
- at least one repository is mature enough to justify issue-to-PR automation.
