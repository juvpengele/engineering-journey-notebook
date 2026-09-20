# Processes & Standards

## PR & Code Understanding Guidelines

### Rule 1 — Know the root cause before opening a PR
Before submitting a pull request, you must be able to clearly answer:
- What is the root cause of the issue? (not just the symptom)
- Why does this specific change fix it?

A PR is not ready for review if the author cannot answer both questions.

### Rule 2 — Understand every line you push to production
- AI tools are allowed for investigation and drafting
- Every line pushed must be understood and defensible
- "This might fix it" is not acceptable

### Rule 3 — Bug replication tests are mandatory
Every bug fix must include a test that:
- Fails before the fix
- Passes after the fix
- Is clearly named

## Ticket Confirmation Process

### When to confirm with the business before starting:
- Ticket describes a symptom, not a clear root cause
- Touches critical paths (auth, billing, data integrity)
- Ambiguous or business-specific jargon
- Estimated more than an hour of work

### When to skip confirmation:
- Typos, copy changes, clearly bounded one-liners
- Cause and fix both stated explicitly
- Repeat patterns fixed the same way before

## React Frontend Guardrails

- ESLint + Prettier — enforced pre-commit via Husky + lint-staged
- TypeScript strict mode enabled
- Vitest coverage thresholds (80% lines, functions, statements / 75% branches)
- Pipeline blocks merge if any check fails
- npm audit for security vulnerabilities
