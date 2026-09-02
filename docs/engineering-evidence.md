# Engineering evidence

A short guide to the code, tests and engineering decisions behind my portfolio.
Choose the path closest to the role you are reviewing.

My professional foundation is IT security and software engineering at Robert
Bosch GmbH. The repositories below are separate portfolio work; they do not
contain Bosch code or establish the scope of a commercial deployment.

## Application security

**Start with authorization behavior you can inspect.**

1. **Evidentia: HTTP authorization and tenant boundaries.** Read
   [EvidenceControllerSecurityTest](https://github.com/giselleevita/evidentia/blob/f6e1115cfd1fc957743fbd657060149af7779469/backend/evidence-service/src/test/kotlin/com/evidentia/evidence/adapters/web/EvidenceControllerSecurityTest.kt)
   alongside
   [EvidenceServiceTest](https://github.com/giselleevita/evidentia/blob/f6e1115cfd1fc957743fbd657060149af7779469/backend/evidence-service/src/test/kotlin/com/evidentia/evidence/application/EvidenceServiceTest.kt).
   The review path covers role checks, invalid lifecycle transitions and access
   through a different tenant.
2. **Agent Security Gate: investigate a control failure and its correction.**
   The [case study](https://github.com/giselleevita/agent-security-gate/blob/main/docs/case-study.md)
   describes an adapter argument-shape mismatch that bypassed argument-level policy,
   its correction and regression coverage. This is a concrete example for discussing
   how a security claim can fail at an integration boundary.
3. **AegisAIS: secure development checks.** Inspect the
   [supply-chain assurance policy](https://github.com/giselleevita/aegisais/blob/main/docs/security/SUPPLY_CHAIN_ASSURANCE.md)
   and [CI workflow](https://github.com/giselleevita/aegisais/blob/main/.github/workflows/ci.yml).
   Discuss scanning, exceptions and the checks that gate later builds.

**Small runnable review:** follow Evidentia's
[JDK 17 test instructions](https://github.com/giselleevita/evidentia/blob/f6e1115cfd1fc957743fbd657060149af7779469/docs/REVIEWER_GUIDE.md).
The evidence-service tests require dependency downloads but no cloud credentials.

**Questions worth discussing:** Where is a permission checked? What happens to a
cross-tenant request? How do you verify remediation? What happens when audit
delivery fails? Which classes of vulnerability do these tests not cover?

The local tests do not prove isolation across every production infrastructure
boundary. Evidentia's
[security boundaries](https://github.com/giselleevita/evidentia/blob/f6e1115cfd1fc957743fbd657060149af7779469/docs/architecture/security-boundaries.md)
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

**Start with a JVM service, then inspect a Python processing pipeline.**

1. **Kotlin/Spring Boot — Evidentia.** Follow the
   [backend reviewer guide](https://github.com/giselleevita/evidentia/blob/f6e1115cfd1fc957743fbd657060149af7779469/docs/REVIEWER_GUIDE.md),
   inspect the [evidence service](https://github.com/giselleevita/evidentia/tree/f6e1115cfd1fc957743fbd657060149af7779469/backend/evidence-service)
   and [state machines](https://github.com/giselleevita/evidentia/blob/f6e1115cfd1fc957743fbd657060149af7779469/docs/architecture/state-machines.md).
   Review REST/controller behavior, lifecycle invariants, persistence migrations
   and the cost of splitting a workflow across services.
2. **Python/FastAPI — AegisAIS.** Run the
   [credential-free detection example](https://github.com/giselleevita/aegisais/blob/main/docs/REVIEWER_GUIDE.md)
   and inspect [its source](https://github.com/giselleevita/aegisais/blob/main/apps/api/scripts/detection_walkthrough.py).
   The examples cover normal movement, an impossible jump, an invalid coordinate
   and an out-of-order timestamp.
3. **Failures and repeated delivery.** Inspect
   [worker boundary tests](https://github.com/giselleevita/aegisais/blob/main/apps/api/tests/test_worker_runtime_boundaries.py)
   and [alert idempotency tests](https://github.com/giselleevita/aegisais/blob/main/apps/api/tests/test_alert_idempotency.py).
   Use the [system overview](https://github.com/giselleevita/aegisais/blob/main/docs/architecture/SYSTEM_OVERVIEW.md)
   to locate APIs, workers, persistence and observability.

**Questions worth discussing:** What happens to duplicate input? How is an invalid
state rejected? Which failure is retried? How would you diagnose a missing alert?
When would a modular monolith be preferable to several services?

AegisAIS uses maritime telemetry rather than charging protocols; it does not
demonstrate OCPP/OCPI expertise. Its small rule walkthrough does not exercise the
full streaming stack or establish production throughput. A non-positive time
interval is skipped by that rule; `NO_ALERT` is not a certificate of valid input.

## Reproduction and review

Evidentia links use the reviewed snapshot `f6e1115`, rather than the moving default
branch. Check out that version before following its setup instructions:

```bash
git clone https://github.com/giselleevita/evidentia.git
cd evidentia
git checkout f6e1115cfd1fc957743fbd657060149af7779469
```

Use the project guides for setup, supported platforms, commands and expected
results. Evidentia's local service tests use JDK 17. AegisAIS's locked backend
environment requires Linux/WSL. ASG's complete verification path also needs the
POSIX-compatible environment described in its guide.

I welcome discussion of the implementations, their limitations and the changes
needed before deployment.
