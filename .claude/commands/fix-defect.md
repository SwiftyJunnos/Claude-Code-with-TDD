---
description: Fix a defect using TDD approach
---

NOTE: Consider using `/tdd fix` instead - part of unified TDD workflow.

# FIX DEFECT WITH TDD

When fixing a defect, follow this process:

1. First write an API-level failing test that demonstrates the bug at a high level
2. Run the test to confirm it fails
3. Write the smallest possible test that replicates the problem
4. Run both tests to confirm they fail
5. Implement the fix
6. Run all tests to confirm both new tests now pass
7. Ensure all existing tests still pass
8. Refactor if needed
9. Commit the fix with both tests

This ensures defects don't reoccur and are covered by tests.

Provide the defect description to begin.
