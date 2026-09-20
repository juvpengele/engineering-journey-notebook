# Azure & Bicep

## Key Concepts

### Bicep Deployment Modes
- **Incremental** — only adds/updates resources, never deletes. Use this always during migration.
- **Complete** — deletes resources not in the template. Dangerous during migration, avoid.

### what-if Command
Preview changes before applying:
```bash
az deployment group what-if \
  --resource-group myResourceGroup \
  --template-file main.bicep \
  --parameters environments/dev.parameters.json
```

### Idempotency
Bicep deployments should be idempotent — running the same template multiple times produces the same result. Always design modules with this in mind.

## GitHub Integration from Azure DevOps

### Create GitHub Release via API
```yaml
- script: |
    VERSION="1.0.0"
    curl -s -X POST \
      -H "Authorization: token $(GITHUB_PAT)" \
      -H "Accept: application/vnd.github.v3+json" \
      https://api.github.com/repos/YOUR_ORG/YOUR_REPO/releases \
      -d '{
        "tag_name": "v'"$VERSION"'",
        "name": "v'"$VERSION"'",
        "generate_release_notes": true
      }'
  displayName: 'Create GitHub Release'
  condition: succeeded()
```

Key points:
- `generate_release_notes: true` auto-generates notes from PR titles and commits
- `condition: succeeded()` — tag only created if deployment succeeded
- Store GitHub PAT as secret variable `$(GITHUB_PAT)` in Azure DevOps

## Naming Convention

| Resource | Dev | Prod |
|----------|-----|------|
| Static Web App | myapp-dev | myapp-prod |
| App Service | myapi-dev | myapi-prod |
| App Insights | myapp-insights-dev | myapp-insights-prod |

## Notes
<!-- Add Azure learnings as you go -->
