---
description: Commit behavioral changes (new functionality)
---

NOTE: Consider using `/tdd commit-behavior` instead - part of unified TDD workflow.

# COMMIT BEHAVIORAL CHANGES

Before committing behavioral changes:

1. Verify ALL tests are passing
2. Verify NO compiler/linter warnings
3. Confirm the commit represents ONE logical unit of work
4. Review the staged changes

Create a commit with message format:
```
feat: [brief description of new functionality]

[Optional longer description including test that was implemented]
```

Or for bug fixes:
```
fix: [brief description of bug fixed]

[Optional longer description including test that was implemented]
```

Use the git-committer skill or create commit manually.

IMPORTANT: Only commit when:
- All tests pass
- No warnings
- Behavioral changes are separate from structural changes
