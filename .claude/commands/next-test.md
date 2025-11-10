---
description: Find and show the next unmarked test in PLAN.md
---

NOTE: Consider using `/tdd next` instead - part of unified TDD workflow.

# FIND NEXT TEST

1. Read PLAN.md
2. Find the first test that is NOT marked with [x]
3. Show the test description to the user
4. Ask if they want to proceed with `/tdd red` to write this test

If PLAN.md doesn't exist, help the user create it with a list of tests to implement.
