# Giselle Evita Koch - Secure Cloud, Backend & AI Governance Engineering

I build secure, maintainable systems for compliance workflows, cloud infrastructure, data pipelines, and AI governance. My projects emphasize tested delivery, auditability, least privilege, CI/CD, and documentation that a reviewer or client team can actually use.

Copenhagen, DK | BSc Computer Science, Cybersecurity | Open to software engineering, cloud, data, AI governance, and security engineering roles

## Reviewer Shortlist

If you only review five repositories, start here:

1. [agent-security-gate](https://github.com/giselleevita/agent-security-gate) - Runtime policy enforcement gateway for tool-using LLM agents with OPA decisions, approval workflows, DLP controls, and tamper-evident audit. **Latest release: v0.4.0** — [technical brief](https://github.com/giselleevita/agent-security-gate/blob/main/docs/technical-brief.md), [blog post](https://github.com/giselleevita/agent-security-gate/blob/main/docs/blog/agent-security-at-tool-boundary.md)
2. [evidentia](https://github.com/giselleevita/evidentia) - Multi-service compliance evidence platform with lifecycle workflows, tenant-scoped audit logging, and a React compliance portal. **15-min review:** [REVIEWER_GUIDE](https://github.com/giselleevita/evidentia/blob/main/docs/REVIEWER_GUIDE.md)
3. [proofrail-evidence-api](https://github.com/giselleevita/proofrail-evidence-api) - FastAPI compliance evidence API for sanctions screening, case workflows, scoped API keys, signed bundles, deployment docs, and test coverage.
4. [secure-docs-aws](https://github.com/giselleevita/secure-docs-aws) - Serverless AWS document-storage pattern using Cognito, API Gateway, Lambda, S3, KMS, DynamoDB ownership checks, and audit logging.
5. [crm-pipeline](https://github.com/giselleevita/crm-pipeline) - HubSpot-to-BigQuery ingestion pipeline with tested transformations, explicit warehouse schemas, and scheduled automation.

## Selected Project Portfolio

| Project | Why it matters | Stack |
|---|---|---|
| [agent-security-gate](https://github.com/giselleevita/agent-security-gate) | Enforces deterministic policy at the LLM tool-call boundary, including approvals, DLP/canary checks, rate limits, and verifiable audit events. | Python, FastAPI, OPA/Rego, Docker, GitHub Actions |
| [evidentia](https://github.com/giselleevita/evidentia) | Multi-service compliance evidence platform with lifecycle workflows, tenant-scoped audit logging, incident tracking, and external integrations. | Kotlin, Spring Boot, React, PostgreSQL, Docker |
| [proofrail-evidence-api](https://github.com/giselleevita/proofrail-evidence-api) | Product-style backend API for compliance evidence, case review, signed audit bundles, scoped access, and operational documentation. | Python, FastAPI, Postgres, S3-compatible storage, Docker, GitHub Actions |
| [secure-docs-aws](https://github.com/giselleevita/secure-docs-aws) | Concrete AWS security pattern for user-owned document access, KMS encryption, presigned URLs, and audit trails. | Terraform, AWS Lambda, API Gateway, Cognito, S3, KMS, DynamoDB |
| [crm-pipeline](https://github.com/giselleevita/crm-pipeline) | Demonstrates a compact client-style data ingestion path with tested transforms, explicit schemas, and scheduled delivery. | Python, HubSpot API, BigQuery, dbt, GitHub Actions |
| [security-compliance-copilot](https://github.com/giselleevita/security-compliance-copilot) | RAG assistant grounded in public NIST/CISA material with citations, guardrails, audit logging, and offline evals. | Python, FastAPI, RAG, Chroma, LLM APIs |

## Supporting Repositories

| Project | Current Scope |
|---|---|
| [terraform-aws-secure-vpc](https://github.com/giselleevita/terraform-aws-secure-vpc) | Focused two-AZ VPC module with public/private subnets, single NAT gateway, ALB, optional WAF association, and CloudWatch VPC Flow Logs. |
| [terraform-aws-iam-baseline](https://github.com/giselleevita/terraform-aws-iam-baseline) | Focused IAM module for an S3 bucket-scoped read-only role. |
| [llm-agent-security-benchmark](https://github.com/giselleevita/llm-agent-security-benchmark) | Research-oriented benchmark for measuring prompt-injection resilience and utility tradeoffs. |
| [vendor-red-team-passport](https://github.com/giselleevita/vendor-red-team-passport) | Focused LLM vendor evaluation and evidence-reporting tool. |
| [network-security-lab](https://github.com/giselleevita/network-security-lab) | Practical security fundamentals lab covering firewall policy, segmentation, IDS/IPS rules, and threat modeling. |

## Private / Deeper Work

| Project | Focus | Access |
|---|---|---|
| ToolShield | Bachelor thesis on prompt-injection detection for tool-using LLM agents, with 200+ tests and ablation work. **15-min review:** [REVIEWER_GUIDE](https://github.com/giselleevita/ToolShield/blob/main/docs/REVIEWER_GUIDE.md), split hygiene tests, metrics module. | Private, available on request |
| AegisAIS | Maritime AIS data integrity checker with anomaly detection, map UI, and alert workflows. **15-min review:** [REVIEWER_GUIDE](https://github.com/giselleevita/aegisais/blob/main/docs/REVIEWER_GUIDE.md), supply-chain CI, detection rules in `apps/api`. | Private, available on request |
| Evidentia | Compliance evidence infrastructure for RBAC, audit logging, and evidence lifecycle workflows. **15-min review:** [REVIEWER_GUIDE](https://github.com/giselleevita/evidentia/blob/main/docs/REVIEWER_GUIDE.md), architecture diagram, evidence lifecycle tests. | [Public repo](https://github.com/giselleevita/evidentia) |

## Working Strengths

- Backend systems: Python, FastAPI, REST APIs, PostgreSQL, structured testing.
- Cloud and infrastructure: Terraform, AWS IAM, VPC, S3, KMS, CloudTrail, Docker, GitHub Actions.
- Data delivery: ingestion pipelines, validation, warehouse modeling, reproducible jobs.
- Security engineering: threat modeling, least privilege, audit logging, OWASP/NIST mapping, security regression tests.
- AI security: prompt-injection defenses, policy-as-code tool gateways, LLM red-teaming, evaluation harnesses.

## How I Build

I care about systems that can be explained, tested, operated, and reviewed. The projects above focus on clear architecture, measurable controls, practical documentation, and engineering choices that would hold up in a client or production-style environment.
