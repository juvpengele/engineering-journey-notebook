# Architecture Decisions

## Template

```
## [Decision title] — [Date]

### Context
What situation led to this decision?

### Options considered
1. 
2. 

### Decision made
What did you choose and why?

### Outcome
What happened? (fill in later)
```

---

## Decisions Log

### Idempotent Sync Endpoint — September 2026

**Context:** Sync system was rejecting requests when a UID was already completed, causing the client to retry infinitely.

**Options considered:**
1. Return 4xx when UID already completed (current broken behavior)
2. Return 200 with completed status when UID already completed (idempotent approach)

**Decision made:** Return 200 with completed status regardless of whether the UID was just completed or already completed. The client should not be able to tell the difference.

**Outcome:** Pending implementation.

---

### Infrastructure as Code with Azure Bicep — September 2026

**Context:** Azure infrastructure was managed manually through the portal — no version history, no reproducibility, environment drift between dev and prod.

**Options considered:**
1. Continue manual portal management
2. Migrate to Azure Bicep with modular structure
3. Use Terraform (cross-cloud)

**Decision made:** Azure Bicep — already on Azure, native integration with Azure DevOps, no additional tooling needed.

**Outcome:** User story created, implementation pending.

---

### Monitoring — Application Insights vs Alternatives — September 2026

**Context:** Need observability for React frontend and .NET backend. Evaluating cost and fit.

**Options considered:**
1. Application Insights — native Azure, easy setup, cost scales with volume
2. Seq — self-hosted, flat cost, best for .NET structured logging
3. Grafana + Loki + Prometheus — open source, free, more setup effort
4. Datadog / New Relic — premium managed options

**Decision made:** Application Insights with adaptive sampling + daily cap for now. Instrument with OpenTelemetry from day one to avoid vendor lock-in.

**Outcome:** To be added to Bicep configuration.
