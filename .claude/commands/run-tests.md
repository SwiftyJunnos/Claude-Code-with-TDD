---
description: Run all tests (excluding long-running tests)
---

NOTE: Consider using `/tdd test` instead - part of unified TDD workflow.

# RUN ALL TESTS

Execute the test suite:

1. Run all tests using the project's test command
2. Exclude long-running/integration tests if specified
3. Report:
   - Number of tests passed/failed
   - Any warnings or errors
   - Overall status (GREEN/RED)
4. If tests fail, show failure details

This command should be run after EVERY code change to ensure nothing broke.
