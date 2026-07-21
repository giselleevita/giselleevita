# Hi, I'm Giselle 👋

**I build enforceable AI security systems** — policy that runs *before* agent tool calls execute, not after damage.

<img src="https://raw.githubusercontent.com/giselleevita/agent-security-gate/main/docs/assets/asg-demo.gif" alt="Agent Security Gate blocking unsafe AI agent tool calls" width="720" />

📍 Copenhagen · open to roles in **Copenhagen & Zürich** (EU citizen — no permit hurdles) · B.Sc. Computer Science, TU Darmstadt · Thesis: *Runtime Policy Enforcement for LLM-based Agents*

> **Start here:** [agent-security-gate](https://github.com/giselleevita/agent-security-gate) — `docker compose up` and see four policy decisions in 30 seconds.

## The stack — Evaluate → Enforce → Govern → Evidence → Ship

| Layer | Repo | What it proves |
|---|---|---|
| **Evaluate** | [vendor-red-team-passport](https://github.com/giselleevita/vendor-red-team-passport) | LLM vendor red-teaming — 10 attack classes, OWASP/NIST mapped, hash-manifested reports (HMAC-signed when configured) |
| **Enforce** | [agent-security-gate](https://github.com/giselleevita/agent-security-gate) ⭐ | Runtime policy gateway for agent tool calls — OPA/Rego, approvals, DLP, hash-chained audit · CI + integration tested · v0.6.0 |
| **Govern** | [security-compliance-copilot](https://github.com/giselleevita/security-compliance-copilot) | Grounded NIST/CISA RAG with citations, guardrails, offline evals |
| **Evidence** | [proofrail-evidence-api](https://github.com/giselleevita/proofrail-evidence-api) | Signed, verifiable compliance evidence bundles |
| **Ship** | [secure-docs-aws](https://github.com/giselleevita/secure-docs-aws) | Secure AWS baseline — Cognito, KMS, IAM least privilege, tfsec/tflint CI |


![ASG CI](https://github.com/giselleevita/agent-security-gate/actions/workflows/ci.yml/badge.svg) ![ASG Integration](https://github.com/giselleevita/agent-security-gate/actions/workflows/integration.yml/badge.svg)

## Writing
- [Why Agent Security Belongs at the Tool-Call Boundary](https://github.com/giselleevita/agent-security-gate/blob/main/docs/blog/agent-security-at-tool-boundary.md)
- [The Denial-Feedback Dilemma — and How to Evaluate It Without Fooling Yourself](https://github.com/giselleevita/agent-security-gate/blob/main/docs/blog/how-to-evaluate-denial-feedback-honestly.md)

## Contact
🌐 [Portfolio](https://giselleevita.github.io/portfolio/) · 💼 [LinkedIn](https://linkedin.com/in/giselle-koch) · ✉️ giselle.evita@gmail.com

🛠 Python · OPA/Rego · FastAPI · AWS · Terraform · Docker · GitHub Actions · 🇩🇪 German (native-level) · 🇬🇧 English (fluent)
