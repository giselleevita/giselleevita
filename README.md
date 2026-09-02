# Hi, I'm Giselle 👋

**Software engineer focused on backend systems and application security.**

I have professional experience in IT security and software engineering at
**Robert Bosch GmbH**, working with backend services, internal tooling,
vulnerability and software issue investigation, Python, Linux, Docker, REST APIs,
testing and CI/CD. I also worked as a technical assistant and Algorithms & Data
Structures tutor at TU Darmstadt.

My projects extend that foundation into **Python/FastAPI and Kotlin/Spring Boot
services, authentication and authorization, and secure AI-agent tool execution**.
I am interested in building reliable software and making its security properties
testable.

📍 **Greater Copenhagen, Denmark · available now for full-time backend, application
security and agent engineering roles · EU citizen**

B.Sc. Computer Science, TU Darmstadt — July 2026
German and Spanish: native · English: near-native · Danish: learning

## Choose a review path

| Focus | Start here | Evidence to inspect |
|---|---|---|
| **Application security** | [Secure development and authorization](docs/engineering-evidence.md#application-security) | Tenant and role checks, a documented authorization defect and fix, dependency-security gates |
| **AI / agent engineering** | [Tool execution, approvals and evaluation](docs/engineering-evidence.md#agent-engineering) | A real callable behind an authorization boundary, failure handling, traceability and bounded evaluation |
| **Backend engineering** | [JVM services and Python data processing](docs/engineering-evidence.md#backend-engineering) | API lifecycle tests, database migrations, stream-worker boundaries, retries and observability |

## Selected engineering projects

| Project | Stack | What it demonstrates |
|---|---|---|
| [**Evidentia**](https://github.com/giselleevita/evidentia/tree/f6e1115cfd1fc957743fbd657060149af7779469) | Kotlin, Spring Boot, PostgreSQL, React/TypeScript | Five-service reference application with evidence lifecycle rules, OIDC/RBAC and tenant-scoped audit events. [Review the service and security tests](https://github.com/giselleevita/evidentia/blob/f6e1115cfd1fc957743fbd657060149af7779469/docs/REVIEWER_GUIDE.md). |
| [**Agent Security Gate**](https://github.com/giselleevita/agent-security-gate/tree/v0.7.1) | Python, FastAPI, OPA/Rego, Docker | Authorization before an agent tool executes, approval workflows and verifiable audit records. [Run the protected-function walkthrough](https://github.com/giselleevita/agent-security-gate/blob/main/docs/security-review-demo-script.md). |
| [**AegisAIS**](https://github.com/giselleevita/aegisais) | Python, FastAPI, PostgreSQL, Redis, React | Maritime telemetry ingestion, explainable anomaly rules and stream processing. [Run a small example and inspect failure boundaries](https://github.com/giselleevita/aegisais/blob/main/docs/REVIEWER_GUIDE.md). |

These are portfolio/reference implementations with documented tests and review
paths. Production deployment, independent validation and domain certification
are separate questions; the linked guides describe the boundaries.

Evidentia links point to the reviewed code snapshot; use the
[checkout instructions](docs/engineering-evidence.md#reproduction-and-review)
to reproduce it.

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
[AI-security portfolio](https://giselleevita.github.io/portfolio/) ·
[giselle.evita@gmail.com](mailto:giselle.evita@gmail.com)

**Copenhagen: available now.**
**Future Switzerland opportunities: Zürich or Zug from June 2027 onward, after May 2027.**
