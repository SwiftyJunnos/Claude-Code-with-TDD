---
description: Commit structural changes (Tidy First)
---

NOTE: Consider using `/tdd commit-tidy` instead - part of unified TDD workflow.

# COMMIT STRUCTURAL CHANGES

Before committing structural changes:

1. Verify ALL tests are passing
2. Verify NO compiler/linter warnings
3. Confirm changes are ONLY structural (no behavior changes)
4. Review the staged changes

Create a commit with message format:
```
refactor: [brief description of structural changes]

[Optional longer description of what was tidied and why]
```

Use the git-committer skill or create commit manually.

IMPORTANT: Only commit when:
- All tests pass
- No warnings
- Changes are purely structural
