# Hi, I'm Giselle 👋

**I build enforceable AI security systems** — policy that runs *before* agent tool calls execute, not after damage.

<img src="https://raw.githubusercontent.com/giselleevita/agent-security-gate/main/docs/assets/asg-demo.gif" alt="Agent Security Gate blocking unsafe AI agent tool calls" width="720" />

📍 Copenhagen · open to roles in **Copenhagen & Zürich** (EU citizen — no permit hurdles) · B.Sc. Computer Science, TU Darmstadt

> **Start here:** [Agent Security Gate v0.7.1 reviewer guide](https://github.com/giselleevita/agent-security-gate/blob/v0.7.1/docs/security-reviewer-guide.md) — a free five-minute protected-function and OPA-outage demonstration with explicit non-claims.

Published AgentDojo evidence is bounded: standalone attacker-goal success was 6/9 without
ASG and 0/9 with it; policy-violating calls were 11 versus 0. Three legitimate held-out
cases were blocked, scored-case security was 100% in both arms, and independent
reproduction is still [requested](https://github.com/giselleevita/agent-security-gate/issues/65).

## The work — Evaluate → Enforce → Ship

| Role | Repo | What it proves |
|---|---|---|
| **Evaluate** | [vendor-red-team-passport](https://github.com/giselleevita/vendor-red-team-passport) | LLM vendor red-teaming — 10 attack classes, OWASP/NIST mapped, hash-manifested reports (HMAC-signed when configured) |
| **Enforce** | [agent-security-gate](https://github.com/giselleevita/agent-security-gate/tree/v0.7.1) ⭐ | Runtime policy gateway for agent tool calls — OPA/Rego, approvals, DLP, hash-chained audit · CI + integration tested · v0.7.1 |
| **Ship** | [secure-docs-aws](https://github.com/giselleevita/secure-docs-aws) | Secure AWS baseline — Cognito, KMS, IAM least privilege, tfsec/tflint CI |


[![ASG CI](https://github.com/giselleevita/agent-security-gate/actions/workflows/ci.yml/badge.svg)](https://github.com/giselleevita/agent-security-gate/actions/workflows/ci.yml)

## Writing
- [Why Agent Security Belongs at the Tool-Call Boundary](https://github.com/giselleevita/agent-security-gate/blob/main/docs/blog/agent-security-at-tool-boundary.md)
- [The Denial-Feedback Dilemma — and How to Evaluate It Without Fooling Yourself](https://github.com/giselleevita/agent-security-gate/blob/main/docs/blog/how-to-evaluate-denial-feedback-honestly.md)

## Contact
🌐 [Portfolio](https://giselleevita.github.io/portfolio/) · 💼 [LinkedIn](https://linkedin.com/in/giselle-koch) · ✉️ giselle.evita@gmail.com

🛠 Python · OPA/Rego · FastAPI · AWS · Terraform · Docker · GitHub Actions · 🇩🇪 German (native-level) · 🇬🇧 English (fluent)
