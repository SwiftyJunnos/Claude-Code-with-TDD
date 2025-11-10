---
description: TDD workflow commands - use /tdd help for tutorial
---

# TDD WORKFLOW COMMAND

Parse the argument and execute the appropriate TDD workflow command.

## ARGUMENT PARSING

Extract the first argument after `/tdd`:
- If no argument or argument is `help`: Show the help/tutorial
- If argument is `go`: Execute tdd-go skill
- If argument is `red`: Execute tdd-red skill
- If argument is `green`: Execute tdd-green skill
- If argument is `refactor`: Execute tdd-refactor skill
- If argument is `tidy`: Execute tdd-tidy skill
- If argument is `cycle`: Execute tdd-cycle skill
- If argument is `next`: Execute next-test command
- If argument is `test` or `tests`: Execute run-tests command
- If argument is `fix` or `fix-defect`: Execute fix-defect command
- If argument is `commit-tidy`: Execute commit-tidy command
- If argument is `commit-behavior`: Execute commit-behavior command
- Otherwise: Show error and suggest `/tdd help`

## HELP/TUTORIAL CONTENT

When argument is `help` or missing, display:

```
# TDD WORKFLOW TUTORIAL

This project follows Kent Beck's Test-Driven Development (TDD) and Tidy First principles.

## QUICK START

1. Create or review PLAN.md with your test cases
2. Run `/tdd go` to start the automated TDD workflow
3. Claude will automatically execute RED → GREEN → REFACTOR → COMMIT

## AVAILABLE COMMANDS

### Main Workflow
- `/tdd go` - Find next test in PLAN.md and execute complete TDD cycle
- `/tdd cycle` - Execute complete TDD cycle (RED → GREEN → REFACTOR)
- `/tdd next` - Find and show the next unmarked test in PLAN.md

### TDD Phases
- `/tdd red` - Write a failing test (RED phase)
- `/tdd green` - Implement minimum code to pass test (GREEN phase)
- `/tdd refactor` - Improve code structure while keeping tests green
- `/tdd tidy` - Make structural changes without changing behavior (Tidy First)

### Testing & Debugging
- `/tdd test` - Run all tests (excluding long-running tests)
- `/tdd fix` - Fix a defect using TDD approach

### Committing
- `/tdd commit-behavior` - Commit behavioral changes (new functionality)
- `/tdd commit-tidy` - Commit structural changes (refactoring)

## TDD CYCLE EXPLAINED

### 1. RED Phase (`/tdd red`)
- Write a failing test that defines desired behavior
- Test should fail because functionality doesn't exist yet
- Use descriptive test names that explain the behavior

### 2. GREEN Phase (`/tdd green`)
- Write the MINIMUM code to make the test pass
- Don't overthink - simplest solution that works
- All tests must pass before moving on

### 3. REFACTOR Phase (`/tdd refactor`)
- Improve code structure while keeping tests green
- Eliminate duplication
- Improve naming and clarity
- Run tests after each change

### 4. TIDY FIRST (Optional)
- Use `/tdd tidy` BEFORE adding new behavior
- Separate structural changes from behavioral changes
- NEVER mix refactoring and new features in same commit

## COMMIT DISCIPLINE

### Structural Changes (Tidy First)
Use `/tdd commit-tidy` for:
- Renaming variables, methods, or classes
- Extracting methods or functions
- Moving code without changing behavior
- Format: `refactor: [description]`

### Behavioral Changes (New Features)
Use `/tdd commit-behavior` for:
- New functionality with passing tests
- Bug fixes with new tests
- Format: `feat: [description]` or `fix: [description]`

## BEST PRACTICES

1. **One test at a time** - Focus on one failing test, make it pass, then refactor
2. **Small steps** - Write minimal code to pass each test
3. **Run tests constantly** - After every change
4. **Keep tests fast** - Fast feedback loop is crucial
5. **Commit frequently** - Small, focused commits
6. **Separate concerns** - Structural vs behavioral changes

## EXAMPLE WORKFLOW

```
/tdd go              # Start: finds next test, writes failing test
                     # Automatically implements code to pass
                     # Automatically refactors if needed
                     # Automatically commits when done
                     # Repeats for next test

# OR do it manually step-by-step:

/tdd next            # See what test is next
/tdd red             # Write the failing test
/tdd test            # Confirm it fails
/tdd green           # Implement minimum code
/tdd test            # Confirm tests pass
/tdd refactor        # Clean up code
/tdd test            # Confirm still passing
/tdd commit-behavior # Commit the new feature
```

## FIXING DEFECTS

```
/tdd fix             # Starts defect fix workflow:
                     # 1. Write API-level failing test
                     # 2. Write smallest test for bug
                     # 3. Implement fix
                     # 4. Verify all tests pass
                     # 5. Refactor if needed
                     # 6. Commit with tests
```

## NEED MORE HELP?

- Read CLAUDE.md for complete TDD principles
- Check PLAN.md for your test cases
- All tests must pass before committing
- Separate structural and behavioral changes
- Use `/tdd help` anytime to see this guide
```

Show this help content to the user.
