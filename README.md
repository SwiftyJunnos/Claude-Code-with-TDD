# Claude TDD Template

A GitHub template for applying Kent Beck's Test-Driven Development (TDD) and Tidy First principles to LLM-assisted development, specifically designed for Claude Code.

## Overview

This template provides a structured workflow for TDD development with Claude as your pair programming partner. It enforces rigorous TDD discipline through custom slash commands and specialized skills, ensuring that code changes follow the Red-Green-Refactor cycle and maintain separation between structural and behavioral changes.

**Credit**: This is based on [Kent Beck's CLAUDE.md](https://github.com/KentBeck/BPlusTree3/blob/ca80e4d85a99cd0af2effe717f709d43e80403bc/rust/docs/CLAUDE.md) from his B+ Tree implementation. This template extends his methodology with practical Claude Code skills and commands.

## Core Methodology

The template enforces these key principles:

- **Red → Green → Refactor**: Always follow the TDD cycle
- **Tidy First**: Separate structural changes from behavioral changes
- **One Test at a Time**: Write one failing test, make it pass, then improve structure
- **Commit Discipline**: Only commit when all tests pass and changes are logically complete
- **Small Steps**: Make the smallest possible change to get tests passing

## Features

### Slash Commands

- `/go` - Start TDD cycle: Find next test in PLAN.md and implement
- `/red` - Write a failing test (RED phase)
- `/green` - Implement minimum code to pass the test (GREEN phase)
- `/refactor` - Improve code structure while keeping tests green
- `/tidy` - Make structural changes without changing behavior (Tidy First)
- `/tdd-cycle` - Execute complete RED → GREEN → REFACTOR cycle
- `/fix-defect` - Fix bugs using TDD approach
- `/next-test` - Show next unmarked test in PLAN.md
- `/run-tests` - Execute all tests (excluding long-running tests)
- `/commit-tidy` - Commit structural changes
- `/commit-behavior` - Commit behavioral changes

### Skills

#### TDD Workflow Skills
- **tdd-go** - Main TDD workflow automation
- **tdd-red** - RED phase: Write failing tests
- **tdd-green** - GREEN phase: Make tests pass with minimum code
- **tdd-refactor** - REFACTOR phase: Improve code structure
- **tdd-cycle** - Complete TDD cycle orchestration
- **tdd-tidy** - Tidy First structural improvements

#### Development Support Skills
- **code-reviewer** - Thorough code review with quality checks
- **git-committer** - Create well-structured commits following conventions
- **pull-request-descriptor** - Generate comprehensive PR descriptions
- **prompt-enhancer** - Enhance prompts with project context
- **skill-creator** - Create new custom skills

## Quick Start

1. **Use this template** to create a new repository
2. **Create a PLAN.md** file listing your tests/features
3. **Create a LANG.md** file specifying test description language (e.g., "Korean", "English")
4. **Run `/go`** to start the TDD cycle

### Example PLAN.md

```markdown
# Test Plan

- [ ] User can create an account
- [ ] User can log in with valid credentials
- [ ] User cannot log in with invalid credentials
- [ ] User can reset password
```

### Example Workflow

```bash
# Start TDD cycle for next test
/go

# Or manually control each phase
/red          # Write failing test
/green        # Implement minimum code
/refactor     # Improve structure
```

## How It Works

1. **Planning**: Define tests in PLAN.md
2. **RED Phase**: Claude writes a failing test for the next unmarked item
3. **GREEN Phase**: Claude implements minimum code to make the test pass
4. **REFACTOR Phase**: Claude improves code structure while keeping tests green
5. **Commit**: Separate commits for structural (Tidy) and behavioral changes
6. **Repeat**: Move to next test in PLAN.md

## File Structure

```
.claude/
├── commands/           # Slash commands for TDD workflow
│   ├── go.md
│   ├── red.md
│   ├── green.md
│   ├── refactor.md
│   └── ...
├── skills/            # Claude Code skills
│   ├── tdd-go/
│   ├── tdd-red/
│   ├── tdd-green/
│   ├── code-reviewer/
│   └── ...
CLAUDE.md              # Main instructions for Claude
PLAN.md               # Your test plan (create this)
LANG.md               # Test description language (create this)
```

## Benefits

- **Disciplined Development**: Enforces TDD best practices automatically
- **Clean Commits**: Separates structural and behavioral changes
- **Quality Assurance**: All tests must pass before committing
- **Documentation**: PLAN.md serves as both roadmap and documentation
- **Reproducible**: Same methodology works across different projects and languages

## Learn More

- [Kent Beck's Original CLAUDE.md](https://github.com/KentBeck/BPlusTree3/blob/ca80e4d85a99cd0af2effe717f709d43e80403bc/rust/docs/CLAUDE.md)
- [Test-Driven Development: By Example](https://www.amazon.com/Test-Driven-Development-Kent-Beck/dp/0321146530)
- [Tidy First?](https://www.oreilly.com/library/view/tidy-first/9781098151232/)
