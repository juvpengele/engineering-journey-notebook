# Team Management

## Key Principles

- Clarity is kindness — clear expectations, clear standards, clear feedback
- Depersonalize the standard, personalize the support
- Catch problems at the cheapest point — before the PR, before the build, before the incident
- Your team's growth is your output

## Processes Put in Place

### Ticket Confirmation Before Implementation
- Before starting any non-trivial ticket, confirm understanding with the business first
- Developer restates the bug in their own words before touching code
- Applies to symptom-based tickets, not clear-cut ones (typos, config changes)

### PR Standards
Before opening a PR, the developer must answer:
1. What is the root cause of the issue?
2. Why does this specific change fix it?

A PR that the author can't explain does not get merged.

### AI Usage Rule
- AI tools are allowed
- Every line pushed to production must be understood and defensible by the author
- "This might fix it" is not acceptable

### Bug Replication Tests
Every bug fix must include a test that:
- Fails before the fix is applied
- Passes after the fix is applied
- Is clearly named to describe the bug it covers

## Lessons Learned

<!-- Add lessons as you go -->
