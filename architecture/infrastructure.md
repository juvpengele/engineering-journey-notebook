# Infrastructure

## Stack

- **Cloud:** Microsoft Azure
- **Frontend:** Azure Static Web App (React)
- **Backend:** Azure App Service (.NET)
- **Monitoring:** Application Insights (OpenTelemetry instrumented)
- **IaC:** Azure Bicep
- **Pipeline:** Azure DevOps
- **Repository:** GitHub

## Environments

| Environment | Purpose |
|-------------|---------|
| dev | Development and staging validation |
| prod | Production |

## Bicep Repository Structure

```
infrastructure/
├── modules/
│   ├── static-web-app.bicep
│   ├── app-service.bicep
│   └── application-insights.bicep
├── environments/
│   ├── dev.parameters.json
│   └── prod.parameters.json
├── main.bicep
└── README.md
```

## Deployment Pipeline

```
PR to main → what-if (preview changes)
merge to main → deploy to dev automatically
manual approval → deploy to prod
successful deploy → create GitHub tag + release notes automatically
```

## Tagging Strategy

- Tags created AFTER successful deployment only
- Tag format: semantic versioning (e.g. v1.0.0)
- Release notes auto-generated from PR titles and commit messages
- No tags on dev branch merges — commit history is sufficient
- Pipeline: Azure DevOps → GitHub API to create tag and release

## Application Insights — Cost Control

- Adaptive sampling enabled
- Daily ingestion cap configured
- Separate instances for dev and prod
- Free tier: 5 GB/month per workspace
- Beyond that: ~$2.76/GB

## Notes

<!-- Add infrastructure learnings as you go -->
