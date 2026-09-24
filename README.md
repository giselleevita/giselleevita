# Hi, I'm Giselle 👋

**I work on AI agent security — stopping LLM agents from taking actions they shouldn't, and measuring honestly whether the defence worked.**

My B.Sc. thesis at TU Darmstadt built a policy enforcement point that evaluates every tool
call an agent proposes before it executes. The part I care most about is the evaluation: my
first benchmark scored 100% → 0% and I discarded it, because I had authored both the attacks
and the policy, which made the result close to tautological. I re-measured against
[AgentDojo](https://github.com/ethz-spylab/agentdojo), an external suite I did not write,
with the protocol frozen in Git before any run — task partition, policy, model digest, seed,
temperature, and disjoint development and held-out splits. Results are reported as counts with
Wilson confidence intervals, and I published the arm that showed no uplift alongside the ones
that did.

Alongside that: LLM red-teaming with OWASP/NIST-mapped attack classes, compliance evidence
systems in Kotlin/Spring Boot, and secure infrastructure in Terraform.

📍 **Greater Copenhagen, Denmark · EU citizen**

B.Sc. Computer Science, TU Darmstadt — July 2026
German and Spanish: native · English: near-native · Danish: learning

## Upstream contributions

Work on shared artifacts rather than my own repositories:

| Where | What | Status |
|---|---|---|
| [ethz-spylab/agentdojo#209](https://github.com/ethz-spylab/agentdojo/issues/209) | `tool_filter` produces zero tool calls with a local model that tool-calls normally without it — 0/40 scored cases, with traces and a ruled-out mechanism | Open |
| [ethz-spylab/agentdojo#184](https://github.com/ethz-spylab/agentdojo/issues/184) | Proposal: a generic pre-execution authorizer seam for `FunctionsRuntime`, with fail-closed semantics and a test plan | Open |
| [OWASP ACS#32](https://github.com/GenAI-Security-Project/agent-control-standard/issues/32) | Measured cost of a fail-closed decision-failure posture: 70 replayed calls, 70 denies, 0 executions | Open |

## Review my work in 90 seconds

1. [**Agent Security Gate**](https://github.com/giselleevita/agent-security-gate) — block an unsafe agent tool call before it runs, then read [what the benchmark does not prove](https://github.com/giselleevita/agent-security-gate/blob/main/docs/benchmark-methodology.md#what-this-does-not-prove).
2. [**DK Security Pack**](https://github.com/giselleevita/dk-procurement-security-pack-generator/blob/main/docs/90_SECOND_DEMO.md) — generate, sign, independently verify, then deliberately tamper with a synthetic procurement evidence pack.
3. [**Vendor Red-Team Passport**](https://github.com/giselleevita/vendor-red-team-passport/blob/main/docs/RESULTS.md) — versioned attack cases and fail-closed release gates, with completed local-model results.

## Choose a review path

| Focus | Start here | Evidence to inspect |
|---|---|---|
| **Application security** | [Secure development and authorization](docs/engineering-evidence.md#application-security) | Tenant and role checks, a documented authorization defect and fix, dependency-security gates |
| **AI / agent engineering** | [Tool execution, approvals and evaluation](docs/engineering-evidence.md#agent-engineering) | A real callable behind an authorization boundary, failure handling, traceability and bounded evaluation |
| **Backend engineering** | [JVM services and Python data processing](docs/engineering-evidence.md#backend-engineering) | API lifecycle tests, database migrations, stream-worker boundaries, retries and observability |

## Selected engineering projects

| Project | Stack | What it demonstrates |
|---|---|---|
| [**Agent Security Gate**](https://github.com/giselleevita/agent-security-gate) | Python, FastAPI, OPA/Rego, Docker | Authorization before agent tool execution, approval workflows, verifiable audit records, and optional OpenTelemetry trace correlation on `main`. [Review the trace runbook](https://github.com/giselleevita/agent-security-gate/blob/main/docs/runbooks/observability.md). |
| [**DK Security Pack**](https://github.com/giselleevita/dk-procurement-security-pack-generator) | Python/FastAPI, React/TypeScript, PostgreSQL | Tenant-scoped evidence collection and Ed25519-signed packs with fail-closed key loading, explicit atomic rotation and offline verification of historical packs. |
| [**Abrahamic**](https://github.com/giselleevita/abrahamic) | Next.js, TypeScript, Prisma, PostgreSQL | Multilingual relational modeling, licensed-content boundaries, role-aware editorial states and immutable audit events. |
| [**Evidentia**](https://github.com/giselleevita/evidentia) | Kotlin, Spring Boot, PostgreSQL, React/TypeScript | Five-service reference application with evidence lifecycle rules, OIDC/RBAC, and leased webhook delivery with bounded retries and recovery metrics. [Review the service and security tests](https://github.com/giselleevita/evidentia/blob/main/docs/REVIEWER_GUIDE.md). |
| [**Vendor Red-Team Passport**](https://github.com/giselleevita/vendor-red-team-passport) | Python, FastAPI, OpenAI-compatible APIs | Evidence-first LLM evaluation with versioned attack cases, fail-closed release gates and sanitized artifacts. [Inspect the completed local-model results](https://github.com/giselleevita/vendor-red-team-passport/blob/main/docs/RESULTS.md). |
| [**AegisAIS**](https://github.com/giselleevita/aegisais) | Python, FastAPI, PostgreSQL, Redis, React | Maritime telemetry ingestion, explainable anomaly rules and stream processing. [Run a small example and inspect failure boundaries](https://github.com/giselleevita/aegisais/blob/main/docs/REVIEWER_GUIDE.md). |

These are portfolio/reference implementations with documented tests and review
paths. Production deployment, independent validation and domain certification
are separate questions; the linked guides describe the boundaries.

[![ASG CI](https://github.com/giselleevita/agent-security-gate/actions/workflows/ci.yml/badge.svg)](https://github.com/giselleevita/agent-security-gate/actions/workflows/ci.yml)
[![AegisAIS CI](https://github.com/giselleevita/aegisais/actions/workflows/ci.yml/badge.svg)](https://github.com/giselleevita/aegisais/actions/workflows/ci.yml)

## How I approach engineering

- Follow a feature from API and data model through tests, error handling and documentation.
- Make authentication, authorization and tenant boundaries explicit.
- Investigate failures, explain the cause and add a regression check.
- Use tests and review to check AI-generated code and distinguish evidence from assumptions.
- Explain technical decisions to developers and other stakeholders.

My strongest project stacks are **Python/FastAPI** and **Kotlin/Spring Boot**, with
Java, TypeScript, SQL, Docker and GitHub Actions in my wider toolkit.

## Agent Security Gate: a closer look

<img src="https://raw.githubusercontent.com/giselleevita/agent-security-gate/main/docs/assets/asg-demo.gif" alt="Agent Security Gate demonstrating policy decisions before AI-agent tool execution" width="720" />

The gate enforces policy at the tool-call boundary. It does not detect prompt
injection. In the published AgentDojo experiment, standalone attacker-goal success
was 6/9 without ASG and 0/9 with it, with 11 versus 0 policy-violating calls.
Three legitimate held-out cases were blocked, and scored-case security was 100%
in both arms. These are bounded, candidate-authored results; independent
reproduction is still [requested](https://github.com/giselleevita/agent-security-gate/issues/65).

- [Case study: defects, fixes and evaluation trade-offs](https://github.com/giselleevita/agent-security-gate/blob/main/docs/case-study.md)
- [Reviewer guide and reproduction prerequisites](https://github.com/giselleevita/agent-security-gate/blob/main/docs/security-reviewer-guide.md)
- [Published benchmark evidence and limits](https://github.com/giselleevita/agent-security-gate/blob/main/docs/benchmark-results/agentdojo-local.md)

## Supporting work

- [secure-docs-aws](https://github.com/giselleevita/secure-docs-aws) — AWS reference infrastructure with Cognito, KMS, IAM and Terraform security checks.
- [hubspot-pipeline](https://github.com/giselleevita/hubspot-pipeline) — Python/PostgreSQL/dbt integration and incremental data modelling.
- [vendor-red-team-passport](https://github.com/giselleevita/vendor-red-team-passport) — structured LLM evaluation and reviewable reports.

## Contact and availability

[GitHub engineering evidence](docs/engineering-evidence.md) ·
[CV-ready evidence bullets](docs/cv-evidence.md) ·
[Portfolio](https://giselleevita.github.io/portfolio/) ·
[giselle.evita@gmail.com](mailto:giselle.evita@gmail.com)

**Copenhagen — available now.**
