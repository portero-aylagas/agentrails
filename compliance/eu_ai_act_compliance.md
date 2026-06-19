# EU AI Act Compliance Audit — Agent Rails

**System:** `agent-rails`  
**Audit type:** First-pass EU AI Act compliance assessment  
**Scope:** Agent Rails umbrella framework and linked repositories  
**Caveat:** This is a consulting-level compliance assessment, not legal advice, not a conformity assessment, and not a certification.

---

## 1. System Brief

Agent Rails is an open-source framework for safer AI-assisted software development.

It does not provide a standalone general-purpose model. It organizes the software development environment around AI coding agents through three pillars:

1. agent-friendly codebase structure;
2. disciplined agent workflow;
3. operational guardrails for mature repositories.

The framework links three repositories:

| Pillar | Repository |
|---|---|
| Agent-Friendly Codebase | https://github.com/portero-aylagas/AI_project_templates |
| Disciplined Agent Workflow | https://github.com/portero-aylagas/agent_skill_safe_project_improvement_system |
| Operational Guardrails | https://github.com/portero-aylagas/agentic-loop-PR |

The system supports developers by helping them structure repositories, guide AI-assisted changes, verify patches, and move mature work into a reviewable issue-to-PR workflow.

The main outputs are:

- repository structures;
- workflow instructions;
- improvement plans;
- generated or assisted code changes;
- verification outputs;
- pull request artifacts;
- review handoff material.

Human review is central. Agent Rails is not intended to automatically merge code, deploy to production, or make final decisions without a maintainer.

## 2. Risk Tier Classification

| Question | Answer |
|---|---|
| Does this system fall under a prohibited AI practice? | No. It is not designed for manipulation, social scoring, biometric identification, biometric categorisation, emotion recognition, predictive policing, or exploitation of vulnerable groups. |
| Does this system operate in an Annex III high-risk area by default? | No. Its default purpose is software development support, not employment selection, education access, credit, healthcare, law enforcement, migration control, democratic processes, or essential-service access. |
| Does it significantly influence decisions about natural persons? | Not in its intended use. It supports software development decisions and requires human review before merge or deployment. |
| Does it generate content or interact through AI-assisted workflows requiring transparency? | Yes. It may generate code, plans, comments, pull request text, and review artifacts. Users should know when AI assistance is used. |
| First-pass risk tier | Limited risk / transparency-relevant. |
| One-sentence justification | Agent Rails is not prohibited and not high-risk in its intended design because it supports human-reviewed software development work, but it uses generative AI workflows and therefore requires transparency, review, and traceability controls. |

### Ambiguity

The classification can change if Agent Rails is repurposed.

If used to develop or operate software in a high-risk regulated domain, the downstream deployment must be reassessed. If it is configured to autonomously merge, deploy, modify production systems, or control safety-critical infrastructure, the risk profile becomes materially higher.

## 3. Role Map

| Role | Entity | Key AI Act obligations |
|---|---|---|
| Provider of Agent Rails framework | The maintainer or organization placing Agent Rails into service under its own name. | Define intended use, document limits, provide user information, maintain transparency controls, and avoid prohibited or high-risk repurposing without reassessment. |
| Deployer | The team or organization using Agent Rails in its own repository workflow. | Use within intended limits, review outputs, maintain human oversight, define protected paths, handle data lawfully, and reassess high-risk contexts. |
| GPAI / model provider | Any upstream LLM provider used by the developer or automation loop. | Upstream model obligations sit with the model provider; downstream repository owners still remain responsible for workflow, review, and deployment decisions. |
| Tooling / automation components | GitHub, CLI tools, CI, coding agents, model APIs, test runners. | Supporting tools do not remove responsibility from the downstream deployer or maintainer. |
| Affected users | Developers, reviewers, maintainers, contributors, and end users of software changed using Agent Rails. | They may be affected by unsafe code changes, review practices, or data exposure if controls fail. |

## 4. High-Risk Obligation Checklist

Agent Rails is **not classified as high-risk** in its current intended design, so the high-risk provider-obligation checklist is not treated as directly applicable.

| High-risk provider obligation | Status for Agent Rails |
|---|---|
| Risk management system | Not required as a high-risk obligation; lightweight risk register still recommended. |
| Data and data governance | Not required as a high-risk obligation; still relevant for repository data, prompts, logs, and GDPR. |
| Technical documentation | Not required as a high-risk obligation; still needed to explain intended use, limitations, and controls. |
| Record-keeping and logging | Not required as a high-risk obligation; recommended for traceability of agent actions. |
| Transparency and user information | Relevant because AI-assisted code, plans, and PR artifacts may be generated. |
| Human oversight | Central design control and should remain mandatory before merge or deployment. |
| Accuracy, robustness, cybersecurity | Not a high-risk obligation in this classification, but necessary for safe software delivery. |
| Conformity assessment | Not applicable unless a downstream use becomes high-risk. |
| EU declaration of conformity / CE marking | Not applicable unless a downstream use becomes high-risk. |
| Registration | Not applicable unless a downstream use becomes high-risk. |
| Post-market monitoring | Not applicable as high-risk obligation; issue tracking and incident review still recommended. |

## 5. Transparency Obligations and Current Design

| Transparency issue | Current state | Assessment |
|---|---|---|
| Users know AI assistance is involved | The framework is explicitly about AI-assisted software development. | Mostly met. Documentation should keep this explicit. |
| AI-generated changes are reviewable | The intended process converts changes into diffs and PRs for human review. | Strong control if preserved. |
| AI-assisted outputs are labelled | Generated PR text, code comments, or review artifacts may not always include durable metadata. | Partial. Add clear AI-assisted markers where useful. |
| Human handoff is visible | The intended automation loop stops for human review rather than automatic merge. | Strong control if not bypassed. |
| Limits are visible | Boundaries such as no auto-merge, no production deployment, and no secrets should be documented. | Mostly met at framework level; must be applied per repository. |

## 6. Mandatory Requirements Summary for Limited-Risk Use

Agent Rails should implement the following practical controls:

| Requirement area | Required control |
|---|---|
| Transparency | Make clear when AI is used to plan, generate, review, or modify code. |
| Human oversight | Require human review before merge or deployment. |
| Traceability | Preserve issue, plan, diff, verification, and PR evidence where possible. |
| Accuracy and robustness | Require tests or documented verification commands for AI-assisted changes. |
| Cybersecurity | Protect secrets, credentials, protected paths, and dependency security. |
| Usage instructions | Document intended use, prohibited use, limitations, and maturity criteria for automation. |
| Reclassification warning | Require downstream reassessment for high-risk domains or autonomous deployment patterns. |

## 7. Gap Analysis and Remediation Plan

### Gap 1 — Durable AI-assisted change disclosure

**Issue:** AI-generated code or PR text may not always carry durable metadata showing that AI assistance was used.

**Current state:** Agent Rails is transparently positioned as AI-assisted, but repository-level artifacts may vary.

**Required state:** Pull requests, generated plans, or automation logs should show when AI assistance contributed materially.

**Remediation:** Add a standard PR footer or checklist item: `AI assistance used: yes/no`, `reviewed by human: yes/no`, `verification run: command/output`.

**Escalation needed:** Low, unless used in regulated delivery contexts.

---

### Gap 2 — Repository-specific protected paths

**Issue:** Agent Rails cannot know every sensitive file in every downstream repository.

**Current state:** Framework-level guidance can define the concept, but downstream teams must configure it.

**Required state:** Each repository should define files or directories that AI agents must not edit without explicit approval.

**Remediation:** Add a protected-paths checklist to repository onboarding.

**Escalation needed:** Medium for production or client repositories.

---

### Gap 3 — Verification quality depends on the repository

**Issue:** The framework depends on tests and verification commands existing.

**Current state:** Templates and safe workflows encourage verification, but normal existing repositories may have weak tests.

**Required state:** Automation should be gated until reliable verification exists.

**Remediation:** Add maturity criteria before using issue-to-PR automation: test command exists, protected paths defined, review owner assigned, failure behavior documented.

**Escalation needed:** No, unless used for safety-critical software.

---

### Gap 4 — Third-party model-provider data flow

**Issue:** Agentic workflows may send issue text, code snippets, logs, or repository metadata to an external model provider.

**Current state:** The framework should make this boundary visible, but provider behavior depends on the chosen tool and configuration.

**Required state:** Users should know what data is sent to model providers, for what purpose, and under what controls.

**Remediation:** Add a standard AI data-flow notice for each downstream repository using Agent Rails.

**Escalation needed:** Yes for commercial or client use; privacy/vendor review recommended.

---

### Gap 5 — Downstream high-risk use

**Issue:** Agent Rails can be applied to many software domains, including domains with higher regulatory impact.

**Current state:** Intended use is general software development support.

**Required state:** Users must reassess if applying the workflow to high-risk systems or regulated decision-making tools.

**Remediation:** Add a reclassification warning in documentation and onboarding.

**Escalation needed:** Yes for regulated domains.

## 8. Conformity Assessment Summary

Agent Rails is classified in this first-pass assessment as **limited risk / transparency-relevant**, not high-risk, for its intended use as a human-reviewed AI-assisted software development framework.

The system does not make final decisions about natural persons, does not determine access to employment, education, healthcare, credit, public services, or legal rights, and does not autonomously merge or deploy software. It provides structure, workflow discipline, and operational guardrails around AI coding agents.

The main compliance controls are transparency, human review, traceability, verification, cybersecurity hygiene, and reclassification warnings for downstream high-risk use. The most important design choice is that AI-assisted changes remain subject to human review before merge or deployment.

Remaining gaps are practical rather than classification-changing in the intended use: durable AI-assisted metadata, repository-specific protected paths, explicit model-provider data flows, and maturity gates before automation. These should be resolved before broad commercial or production use.

## 9. Technical Documentation Outline

A full technical documentation package for Agent Rails would contain:

1. System overview and intended use
2. Three-pillar architecture
3. Linked repository inventory
4. Supported workflows
5. Out-of-scope and prohibited uses
6. Data-flow description for prompts, code snippets, issues, logs, and PR artifacts
7. Human oversight model
8. Verification and test requirements
9. Protected-path and secrets-handling policy
10. Automation maturity criteria
11. Logging and traceability model
12. Known limitations
13. Risk register
14. Security controls
15. Incident handling procedure
16. Downstream reclassification checklist
17. Change-management and release notes

## 10. Conclusion

**Final first-pass classification:** Limited risk / transparency-relevant.

Agent Rails is not high-risk in its intended design because it supports human-reviewed software development work rather than regulated decisions about people. The main compliance work is transparency, human oversight, traceability, privacy governance, cybersecurity hygiene, and clear warnings against uncontrolled downstream repurposing.
