# GDPR Audit — Agent Rails

**System:** `agent-rails`  
**Audit type:** First-pass GDPR/data protection review  
**Scope:** Agent Rails umbrella framework and linked repositories  
**Caveat:** This is a consulting-level assessment, not legal advice.

---

## 1. Data Processing Brief

Agent Rails is an open-source framework for safer AI-assisted software development. It helps teams structure repositories, guide AI coding agents through disciplined workflows, and optionally add issue-to-PR automation when a repository is mature.

The framework may process or expose personal data through normal software collaboration channels: GitHub issues, pull requests, commits, comments, logs, AI prompts, and generated outputs.

Agent Rails should not require sensitive personal data. However, personal data may appear accidentally in repository content, issue descriptions, commit metadata, comments, logs, or prompts sent to AI providers.

Human review and data minimization are core controls. Agent Rails should not be used to process secrets, private customer data, production databases, or unnecessary personal data through AI prompts.

## 2. Personal Data Inventory

| Data category | Source | Purpose(s) | Retention period | Crosses EU border? |
|---|---|---|---|---|
| GitHub usernames | Issues, PRs, commits, comments | Attribution, review, audit trail | GitHub retention / repository history | Possible, depending on GitHub infrastructure and account settings |
| Contributor names | Commits, profiles, PRs | Attribution, review, accountability | Repository history unless rewritten | Possible |
| Commit emails | Git commits | Attribution and version control | Repository history unless rewritten | Possible |
| Issue text | Maintainers or contributors | Define tasks and success criteria | Public or private repository retention | Possible if sent to AI tools |
| Pull request text | Maintainers, contributors, AI tools | Review, discussion, change tracking | Repository retention | Possible if sent to AI tools |
| Review comments | Reviewers and maintainers | Review, quality control, audit trail | Repository retention | Possible |
| Logs and terminal output | Local workflow, CI, automation loop | Debugging, verification, traceability | Should be minimized and time-limited | Possible if stored in cloud CI or sent to AI provider |
| Prompt payloads | Developer, issue content, code snippets | AI-assisted planning, review, implementation | Depends on model provider and local logging | Yes / possible |
| AI-generated outputs | AI coding tools | Plans, code patches, PR text, review notes | Repository, local logs, or provider traces | Yes / possible |
| Accidental personal data in code/comments | Existing repository content | Not an intended input; may be included accidentally | Depends on repository and provider retention | Yes / possible if sent to AI provider |
| Secrets or credentials | Existing files, logs, environment | Not intended; should be excluded | Should not be processed or retained | Yes / possible if controls fail |

Purpose limitation flag: repository data used to support a scoped coding task should not be reused for unrelated model training, analytics, or product improvement unless a separate lawful basis and notice exist.

## 3. Data Flow Map

| Step | Data involved | Source | Destination | Control |
|---|---|---|---|---|
| Repository setup | Repository structure, prompts, schemas, tests, docs | Maintainer | Local repository / GitHub | Avoid real personal data in examples. |
| Safe improvement workflow | Issue text, file paths, selected code snippets, verification output | Developer / repository | Local agent session and possibly AI provider | Scope task and minimize prompt payload. |
| AI-assisted planning | Task description, relevant context | Issue / maintainer | AI model provider or local model | Do not include secrets or unnecessary personal data. |
| Patch generation | Code snippets, file context, task plan | Repository | AI model provider or local model | Restrict files and review diff. |
| Verification | Test output, logs, errors | Local environment / CI | Local logs, CI logs, possibly PR comments | Redact sensitive output. |
| Pull request creation | Diff, PR text, comments, reviewer metadata | Repository / AI tool | GitHub | Human review before merge. |
| Automation loop | Issue, branch, logs, PR metadata | GitHub / local tool | GitHub, CI, AI provider | Use maturity gate and protected paths. |

## 4. Processing Activities Register

| Processing activity | Personal data | Purpose | Proposed lawful basis | Retention | Recipients |
|---|---|---|---|---|---|
| Repository collaboration | Usernames, names, commit emails, comments | Software collaboration and review | Legitimate interest, or contract in service context | Repository history | GitHub, repository maintainers |
| AI-assisted issue analysis | Issue text, possible user identifiers | Plan scoped software changes | Legitimate interest, or contract in service context | Provider and local retention should be minimized | AI provider, local tooling |
| AI-assisted code generation | Code snippets, prompts, logs | Generate or suggest scoped changes | Legitimate interest, or contract in service context | Minimized; avoid persistent prompt logs where possible | AI provider, local tooling |
| Verification and debugging | Logs, error messages, contributor metadata | Validate changes and diagnose failures | Legitimate interest | Time-limited where possible | CI provider, maintainers |
| Pull request review | PR text, comments, reviewer identity | Human review and accountability | Legitimate interest | Repository history | GitHub, maintainers |
| Security review | Logs, dependency data, incident reports | Prevent unsafe changes and secret exposure | Legitimate interest / legal obligation where applicable | Time-limited according to security policy | Maintainers, security reviewers |

## 5. Legal Basis Assessment

| Purpose | Proposed lawful basis | One-line justification | Flag for legal review? |
|---|---|---|---|
| Maintain public repository collaboration | Legitimate interest | Open-source collaboration requires attribution, review, and discussion. | Low / medium |
| Use AI tools to assist scoped development | Legitimate interest | Developers have a legitimate interest in improving productivity and quality with safeguards. | Medium |
| Provide Agent Rails as a paid implementation or support service | Contract | Processing may be necessary to provide the requested setup or support service. | Yes |
| Process logs for debugging and security | Legitimate interest | Minimal logs may be needed to maintain security and reliability. | Medium |
| Send repository context to external AI providers | Legitimate interest or contract, plus processor safeguards | AI workflows may require model processing, but data minimization and vendor controls are required. | Yes |
| Use contribution data for unrelated analytics or product improvement | TBD | This is separate from core collaboration and should not be assumed. | Yes |

### Legitimate Interests Assessment — AI-assisted development workflow

| Test | Answer |
|---|---|
| Legitimate interest | Improve software development productivity, reviewability, and quality while reducing unsafe AI-generated changes. |
| Necessity | Only repository context needed for the scoped task should be processed. Full repositories, secrets, private data, and unrelated files should not be sent to AI providers unless strictly necessary and approved. |
| Balancing test | Contributor and user privacy risks are reduced if prompts are minimized, public examples are sanitized, logs are limited, and human review remains mandatory. |

## 6. Data Protection Impact Assessment

Highest-risk processing activity:

> Sending repository context, issue text, logs, or code snippets to an external AI provider for planning, code generation, review, or remediation.

### 6.1 Description of Processing

The workflow may send selected task context, issue descriptions, code snippets, error messages, and verification output to an AI model provider. The model returns plans, suggested changes, explanations, or review comments.

### 6.2 Necessity and Proportionality

The processing is necessary only where AI assistance is used for scoped development work. It is not necessary to send secrets, private customer data, production data, full logs, or unrelated files.

The proportional design is:

- send the minimum relevant context;
- avoid secrets and personal data;
- use local or private models where appropriate;
- review output before merge or deployment;
- define repository-specific protected paths.

### 6.3 Risks to Data Subjects

| Risk | Impact | Mitigation | Residual risk |
|---|---|---|---|
| Personal data in public issues is sent to an AI provider | Exposure beyond intended audience | Issue hygiene, redaction, prompt minimization | Medium |
| Commit emails or contributor identity appear in prompts/logs | Unnecessary identity processing | Avoid including metadata unless needed | Low / medium |
| Secrets included in logs or prompts | Credential compromise and data breach | Secret scanning, `.env.example`, protected paths, redaction | Medium |
| Provider retention or non-EU transfer is unclear | Transfer and processor compliance risk | DPA, transfer mechanism, provider review | Medium |
| Incorrect AI-generated output affects downstream users | Software defect or security risk | Human review, tests, CI, rollback process | Medium |
| Public repository history prevents easy deletion | Rights-handling friction | Document limitation, support removal where feasible | Medium |

### 6.4 Mitigation Measures

- Do not include secrets in repositories, issues, prompts, or logs.
- Use `.env.example` instead of real environment files.
- Keep runtime data and logs out of Git.
- Minimize prompt payloads to task-relevant context.
- Redact personal data before using public examples.
- Define protected paths per repository.
- Require human review before merge or deployment.
- Document AI provider use and transfer mechanisms before commercial or client use.
- Keep logs time-limited where feasible.
- Provide a process for correction or removal requests where practical.

### 6.5 Residual Risk Rating

Residual risk: **medium**.

Reason: Agent Rails can be operated safely with strong data minimization and review controls, but public repository collaboration, third-party AI providers, logs, and immutable Git history create privacy friction that cannot be fully eliminated.

## 7. Data Subject Rights

| Right | Support approach | Gap |
|---|---|---|
| Access | Identify issues, PRs, comments, commits, and logs containing the person’s data. | Harder if data is spread across GitHub and external tools. |
| Rectification | Correct inaccurate comments, issue text, docs, or generated outputs where feasible. | Git history may preserve older versions. |
| Erasure | Remove or redact data from issues, comments, docs, logs, and examples where feasible. | Public forks, commit history, and provider retention may limit full erasure. |
| Portability | Export relevant structured records where feasible. | Not all GitHub or provider data is controlled by Agent Rails. |
| Objection | Allow contributors or users to object to unnecessary processing, especially AI-provider processing. | Requires clear contact and process in downstream use. |
| Restriction | Pause use of disputed data in prompts, examples, or docs. | Requires operational discipline. |
| Automated decision-making | Agent Rails should not make solely automated decisions with legal or similarly significant effects. | Must reassess if used in regulated decision workflows. |

## 8. Third-Party Transfers

| Recipient | Data potentially sent | Purpose | Transfer concern | Required control |
|---|---|---|---|---|
| GitHub | Usernames, commits, emails, issues, PRs, comments | Repository hosting and collaboration | Public visibility and possible non-EU processing | Repository privacy settings, account settings, issue hygiene. |
| AI model provider | Prompts, code snippets, logs, issue text, AI outputs | Planning, code generation, review, remediation | Provider retention, processor role, non-EU transfer | DPA, transfer mechanism, data minimization. |
| CI provider | Logs, test output, commit metadata | Verification | Logs may contain sensitive data | Redaction, log retention limits, secret masking. |
| Local developer machine | Repository files, prompts, logs | Development and review | Device access and local storage risk | Local security, access control, disk encryption where appropriate. |
| Future hosted dashboard or analytics provider | Usage metadata, workflow metrics | Adoption measurement and reporting | New processor and analytics purpose | Separate review before implementation. |

International transfer note: external AI and cloud providers may process data outside the EEA unless contract, region, and transfer safeguards prove otherwise. A production or client-facing use should document SCCs, adequacy mechanisms, EU-US Data Privacy Framework certification where applicable, and transfer risk assessment.

## 9. Law Stacking Check

| Law | Applies? | Reason |
|---|---|---|
| GDPR | Yes, where personal data is processed beyond purely personal use. | GitHub identity data, commit metadata, issues, PRs, logs, and prompts may contain personal data. |
| EU AI Act | Likely limited-risk / transparency-relevant in intended use. | The system supports AI-assisted software development and requires human review. |
| ePrivacy | Usually no / maybe. | May apply if hosted services, analytics, cookies, or communications monitoring are added. |
| Data Act | Usually not central. | No connected product or IoT-generated data is central to Agent Rails. Cloud switching may matter only if hosted commercially. |

## 10. Accountability Test

| Document / evidence | Exists? | Gap |
|---|---|---|
| Data inventory | Partial | This audit provides a first version. |
| Processing register | Partial | Needs adaptation for each downstream repository or service use. |
| Privacy notice | Not included | Needed before client-facing or hosted use. |
| DPA with AI provider | Unknown | Must be confirmed before processing client or non-public data. |
| International transfer mechanism | Unknown | Must be documented for external providers. |
| Legitimate Interests Assessment | Partial | Included here at first-pass level. |
| DPIA | Partial | This document provides first-pass DPIA content. |
| Retention schedule | Partial | Needs concrete retention periods per deployment. |
| Subject rights workflow | Partial | Needs owner, contact process, and operational procedure. |
| Security/access control documentation | Partial | Needs repository-specific protected paths and secret-handling controls. |

Accountability conclusion: Agent Rails has a defensible privacy posture if used with sanitized public repositories, prompt minimization, secret exclusion, and human review. It is not enough for client-facing or hosted use without provider contracts, transfer documentation, retention rules, and rights-handling procedures.

## 11. Data Protection by Design Checklist

Highest-risk processing activity: sending repository context, issue text, logs, or code snippets to an external AI provider.

| Design principle | Current state | Pass / Fail / Unknown | Required change |
|---|---|---|---|
| Data minimisation | Framework recommends scoped tasks, but each AI call depends on user/tool configuration. | Partial | Define prompt minimization rules. |
| Purpose binding | Purpose is AI-assisted software development, but unrelated analytics must be separated. | Partial | Add policy against unrelated reuse without separate basis. |
| Access controls | Depends on repository settings and developer environment. | Unknown | Define access model for private/client repositories. |
| Retention enforcement | GitHub and provider retention may vary. | Unknown | Define log and prompt retention expectations. |
| Subject rights workflow | Not formalized in framework docs. | Partial | Add rights-handling procedure for public and hosted contexts. |
| Incident response | Not formalized. | Unknown | Add breach and secret-exposure procedure before production use. |
| Human review | Central design principle. | Pass | Preserve no-auto-merge and no-auto-deploy boundaries. |

## 12. Conclusion

Agent Rails can be operated with a moderate privacy risk profile if it is used for sanitized repositories, scoped tasks, minimized prompts, and human-reviewed changes.

The main GDPR risks are personal data in public issues or prompts, unclear AI-provider transfer terms, logs containing sensitive information, and difficulty removing data from public Git history.

Before commercial, hosted, or client-facing use, the required next steps are:

1. define a privacy notice;
2. document provider contracts and transfer mechanisms;
3. define retention periods;
4. formalize data subject rights handling;
5. define repository-specific protected paths and secret rules;
6. avoid sending non-public or sensitive data to AI providers without review.
