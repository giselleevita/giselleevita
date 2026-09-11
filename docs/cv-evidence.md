# CV-ready engineering evidence

These bullets are designed to be selected and adapted for a specific vacancy. Keep two or three under **Selected Projects**; do not paste all of them into one CV.

## AI security / applied ML

- Built a reproducible prompt-injection evaluation toolkit with deterministic datasets, attack-family and tool-holdout protocols, machine-readable metrics, and hashed configuration provenance; published a key-free static results explorer with fail-closed deployment checks.
- Separated detector evaluation from authorization by mapping model scores to explicit read, write, and privileged-tool policies, documenting false-positive and single-seed limitations rather than presenting point estimates as production guarantees.

Evidence: [ToolShield explorer](https://giselleevita.github.io/ToolShield/) · [repository](https://github.com/giselleevita/ToolShield) · [90-second review](https://github.com/giselleevita/ToolShield/blob/main/docs/90_SECOND_DEMO.md)

## Backend / application security

- Developed a FastAPI and React evidence-pack system with tenant scoping, bounded uploads, OAuth state/PKCE controls, rate limiting, secure headers, and disposable synthetic-demo restrictions.
- Designed a versioned Ed25519-signed pack format with SHA-256 artifact hashes and offline verification; automated a negative proof showing that modifying an artifact causes verification to fail.

Evidence: [repository](https://github.com/giselleevita/dk-procurement-security-pack-generator) · [engineering case study](https://github.com/giselleevita/dk-procurement-security-pack-generator/blob/main/docs/engineering-case-study.md) · [90-second review](https://github.com/giselleevita/dk-procurement-security-pack-generator/blob/main/docs/90_SECOND_DEMO.md)

## Full-stack / data integrity

- Implemented a Next.js, Prisma, and PostgreSQL editorial workflow with database-backed states, role-aware transitions, transactional audit events, and public APIs restricted to published records.
- Enforced public-corpus licensing metadata at seed and API boundaries and made the demonstration seed cleanly idempotent, with a two-pass PostgreSQL verification gate in CI.

Evidence: [live application](https://abrahamic.vercel.app) · [repository](https://github.com/giselleevita/abrahamic) · [90-second review](https://github.com/giselleevita/abrahamic/blob/main/docs/90_SECOND_DEMO.md)

## Accurate summary line

Software engineer with Bosch experience and a TU Darmstadt Computer Science degree, building Python/FastAPI and TypeScript/PostgreSQL systems with explicit authorization, evidence integrity, and reproducible security testing. Native German and Spanish; near-native English; EU citizen currently in Copenhagen and targeting Zürich/Zug from June 2027.

## Claims to avoid

- Do not call a repository “production proven,” independently validated, or customer deployed unless that later becomes true.
- Do not describe single-seed neural results as statistically stable.
- Do not imply the public procurement demo provides durable key custody or storage.
- Do not call reader notes licensed scripture translations or AI output peer-reviewed scholarship.
