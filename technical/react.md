# React

## Stack
- React (frontend)
- TypeScript (strict mode)
- Vitest (testing)
- ESLint + Prettier (code quality)
- Husky + lint-staged (pre-commit hooks)

## Quality Setup

### ESLint Plugins
- eslint-plugin-react
- eslint-plugin-react-hooks
- eslint-plugin-jsx-a11y

### Coverage Thresholds
```json
coverage: {
  thresholds: {
    lines: 80,
    functions: 80,
    branches: 75,
    statements: 80
  }
}
```

### TypeScript Strict Mode
```json
{
  "compilerOptions": {
    "strict": true,
    "noImplicitAny": true,
    "strictNullChecks": true
  }
}
```

### Pre-commit Hook (lint-staged)
```json
"lint-staged": {
  "*.{js,jsx,ts,tsx}": [
    "eslint --fix",
    "prettier --write"
  ]
}
```

## Testing Principles
- Every bug fix must have a replication test
- Test fails before fix, passes after fix
- Name tests descriptively: `should return 200 when UID is already completed`

## Notes
<!-- Add React learnings as you go -->
