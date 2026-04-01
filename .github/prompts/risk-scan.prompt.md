# Skill: Risk Assessment Scan

Scan the provided file or module and flag migration risks only.
Do not generate migration code. Output a risk register.

## What to look for
- Cross-schema database access
- Stored procedure calls with complex parameters
- Shared mutable state (static classes, caches, session state)
- File system access
- Hardcoded connection strings or config
- Direct SQL strings in code (not via stored procs)
- Third-party library dependencies that have no Java equivalent
- Windows-specific APIs

## Output format

### Risk Register: [File/Module Name]

| Risk | Location | Severity | Notes |
|------|----------|----------|-------|
```

---

## How to use these together in practice

The workflow becomes:
```
1. Open a .NET controller file in VS Code
2. Copilot already knows your project from copilot-instructions.md
3. Type: "Use #scan-feature.prompt.md on this controller"
4. Save the output as docs/features/[FeatureName].md
5. Paste stored proc definitions and run: "Use #document-stored-proc.prompt.md"
6. Once all docs exist: "Use #migrate-controller.prompt.md using this doc as input"
