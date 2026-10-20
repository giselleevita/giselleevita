# Engineering evidence

A short guide to the code, tests and engineering decisions behind my portfolio.
Choose the path closest to the role you are reviewing.

My professional foundation is IT security and software engineering at Robert
Bosch GmbH. The repositories below are separate portfolio projects rather than
evidence of Bosch deployments.

## Application security

**Start with authorization behavior you can inspect.**

1. **Evidentia: HTTP authorization and tenant boundaries.** Read
   [EvidenceControllerSecurityTest](https://github.com/giselleevita/evidentia/blob/main/backend/evidence-service/src/test/kotlin/com/evidentia/evidence/adapters/web/EvidenceControllerSecurityTest.kt)
   alongside
   [EvidenceServiceTest](https://github.com/giselleevita/evidentia/blob/main/backend/evidence-service/src/test/kotlin/com/evidentia/evidence/application/EvidenceServiceTest.kt).
   The review path covers role checks, invalid lifecycle transitions and access
   through a different tenant.
2. **Agent Security Gate: investigate a control failure and its correction.**
   The [case study](https://github.com/giselleevita/agent-security-gate/blob/main/docs/case-study.md)
   describes an adapter argument-shape mismatch that bypassed argument-level policy,
   its correction and regression coverage. This is a concrete example for discussing
   how a security claim can fail at an integration boundary.
**Small runnable review:** follow Evidentia's
[JDK 17 test instructions](https://github.com/giselleevita/evidentia/blob/main/docs/REVIEWER_GUIDE.md).
The evidence-service tests require dependency downloads but no cloud credentials.

**Questions worth discussing:** Where is a permission checked? What happens to a
cross-tenant request? How do you verify remediation? What happens when audit
delivery fails? Which classes of vulnerability do these tests not cover?

The local tests do not prove isolation across every production infrastructure
boundary. Evidentia's
[security boundaries](https://github.com/giselleevita/evidentia/blob/main/docs/architecture/security-boundaries.md)
also document that business writes and audit delivery are not one atomic transaction.

## Agent engineering

**Start with the boundary between an agent decision and a real side effect.**

1. Follow ASG's
   [protected-function walkthrough](https://github.com/giselleevita/agent-security-gate/blob/main/docs/security-review-demo-script.md).
   It pins the walkthrough to v0.7.1 and includes environment setup.
2. Inspect the
   [authorization adapter](https://github.com/giselleevita/agent-security-gate/blob/v0.7.1/adapters/tool_authorization.py)
   and [decision handling](https://github.com/giselleevita/agent-security-gate/blob/v0.7.1/app/decision.py).
   Review the allow/deny/approval contract, argument binding and failure behavior.
3. Compare the
   [published benchmark](https://github.com/giselleevita/agent-security-gate/blob/main/docs/benchmark-results/agentdojo-local.md)
   with the [case study](https://github.com/giselleevita/agent-security-gate/blob/main/docs/case-study.md).
   Look at legitimate task completion as well as blocked actions.

**Questions worth discussing:** What reaches the callable? What happens if OPA
is unavailable? How are privileged actions approved? What is logged? How can
an evaluation appear successful without showing a useful improvement?

This demonstrates agent authorization and evaluation work. It is not evidence
of operating a large RAG or multi-agent product. The published benchmark is
candidate-authored, has a documented utility cost and does not establish
general prompt-injection prevention.

## Backend engineering

**Start with a JVM service.**

1. **Kotlin/Spring Boot — Evidentia.** Follow the
   [backend reviewer guide](https://github.com/giselleevita/evidentia/blob/main/docs/REVIEWER_GUIDE.md),
   inspect the [evidence service](https://github.com/giselleevita/evidentia/tree/main/backend/evidence-service)
   and [state machines](https://github.com/giselleevita/evidentia/blob/main/docs/architecture/state-machines.md).
   Review REST/controller behavior, lifecycle invariants, persistence migrations
   and the cost of splitting a workflow across services.

## Operational failure handling

These `main`-branch reference implementations expose concrete failure behavior:

1. [ToolShield API tests](https://github.com/giselleevita/ToolShield/blob/main/tests/test_demo.py)
   cover bounded requests, model readiness, authenticated configuration and
   required audit-write failure.
2. [Agent Security Gate's observability runbook](https://github.com/giselleevita/agent-security-gate/blob/main/docs/runbooks/observability.md)
   shows W3C trace/request correlation while excluding prompts, arguments,
   tenant IDs and credentials from span attributes.
3. [Evidentia's webhook migration](https://github.com/giselleevita/evidentia/blob/main/backend/integration-service/src/main/resources/db/migration/V3__webhook_delivery_leases.sql)
   and [dispatch-policy tests](https://github.com/giselleevita/evidentia/blob/main/backend/integration-service/src/test/kotlin/com/evidentia/integration/application/WebhookDispatchPolicyTest.kt)
   exercise due-delivery leasing, retry classification, lease recovery and
   terminal failures without holding a database transaction across HTTP I/O.
These controls and tests improve inspectability; they do not establish a
production SLO, external certification or independent security validation.

## Reproduction and review

Use the project guides for setup, supported platforms, commands and expected
results. Evidentia's local service tests use JDK 17. ASG's complete verification path also needs the
POSIX-compatible environment described in its guide.

I welcome discussion of the implementations, their limitations and the changes
needed before deployment.
