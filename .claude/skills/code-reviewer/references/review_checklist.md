# Code Review Checklist

## Requirements Compliance
- [ ] All features from requirements document implemented
- [ ] Acceptance criteria met
- [ ] No scope creep (only required features)
- [ ] Edge cases handled as specified

## Code Quality

### Readability
- [ ] Code is self-documenting with clear variable/function names
- [ ] Complex logic has explanatory comments
- [ ] Consistent formatting throughout
- [ ] No commented-out code
- [ ] No debug statements (console.log, debugger, etc.)

### Structure
- [ ] Functions are single-purpose and focused
- [ ] Proper separation of concerns
- [ ] DRY principle followed (no code duplication)
- [ ] Appropriate use of abstractions
- [ ] Files are appropriately sized (not too large)

### TypeScript (if applicable)
- [ ] Proper type annotations
- [ ] No `any` types (or justified if used)
- [ ] Interfaces/types properly defined and exported
- [ ] Generic types used appropriately
- [ ] No TypeScript errors or warnings

## Best Practices

### React (if applicable)
- [ ] Hooks used correctly (dependencies, rules of hooks)
- [ ] Proper component lifecycle management
- [ ] No unnecessary re-renders
- [ ] Props properly typed
- [ ] State management appropriate for scope
- [ ] Effects have proper cleanup

### Error Handling
- [ ] All error cases handled
- [ ] Meaningful error messages
- [ ] Proper logging (using Logger, not console)
- [ ] No unhandled promise rejections
- [ ] Try-catch blocks where appropriate

### Performance
- [ ] No performance bottlenecks
- [ ] Appropriate use of memoization
- [ ] No unnecessary computations
- [ ] Efficient algorithms and data structures
- [ ] Lazy loading where beneficial

### Security
- [ ] No hardcoded secrets or credentials
- [ ] Input validation and sanitization
- [ ] No XSS vulnerabilities
- [ ] No SQL injection risks
- [ ] Proper authentication/authorization checks
- [ ] Sensitive data properly handled

## Testing Readiness
- [ ] Code is testable (proper structure)
- [ ] Dependencies can be mocked
- [ ] Functions are pure where possible
- [ ] Side effects isolated and manageable
- [ ] Test cases can be derived from code

## Project Standards
- [ ] Follows project naming conventions
- [ ] Matches existing code patterns
- [ ] Uses project utilities and abstractions
- [ ] Import statements organized properly
- [ ] File location appropriate for project structure

## Documentation
- [ ] Complex functions have JSDoc comments
- [ ] Non-obvious logic explained
- [ ] Public APIs documented
- [ ] README updated if needed
- [ ] Breaking changes noted

## Common Issues to Watch For
- [ ] Off-by-one errors in loops
- [ ] Race conditions in async code
- [ ] Memory leaks (event listeners, subscriptions)
- [ ] Infinite loops or recursion without base case
- [ ] Incorrect null/undefined handling
- [ ] Timezone issues in date handling
