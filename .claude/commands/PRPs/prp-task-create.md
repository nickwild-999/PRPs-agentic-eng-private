# Create TASK PRP (Advanced)

Generate a comprehensive task list for focused changes with validation.

## Task: $ARGUMENTS

## Analysis Process

1. **Scope Definition**
   - Identify all affected files
   - Map dependencies
   - Check for side effects
   - Note test coverage

2. **Pattern Research with Context7**
   - **Auto-detect technologies**: Identify frameworks/libraries involved in the task
   - **Resolve library IDs**: Use mcp__context7__resolve-library-id for detected technologies
   - **Fetch task-specific docs**: Use mcp__context7__get-library-docs focusing on the specific functionality being modified
   - **Include in task context**: Integrate current documentation into task implementation
   - Find similar changes in history
   - Identify conventions to follow (enhanced with Context7 patterns)
   - Check for helper functions
   - Review test patterns

3. **User Clarification**
   - Confirm change scope
   - Verify acceptance criteria
   - Check deployment considerations
   - Identify blockers

## PRP Generation

**READ**
Using TASK_PRP/PRPs/prp_task.md format:

### Context Section

```yaml
context:
  context7_docs:
    - library: [detected framework]
      documentation: [relevant sections]
      focus: [specific methods/patterns]

  docs:
    - url: [API documentation]
      focus: [specific methods]

  patterns:
    - file: existing/example.py
      copy: [pattern to follow]

  gotchas:
    - issue: "Library requires X"
      fix: "Always do Y first"
```

### Task Structure

```
ACTION path/to/file:
  - OPERATION: [specific change]
  - VALIDATE: [test command]
  - IF_FAIL: [debug strategy]
  - ROLLBACK: [undo approach]
```

### Task Sequencing

1. **Setup Tasks**: Prerequisites
2. **Core Changes**: Main modifications
3. **Integration**: Connect components
4. **Validation**: Comprehensive tests
5. **Cleanup**: Remove temp code

### Validation Strategy

- Unit test after each change
- Integration test after groups
- Performance check if relevant
- Security scan for sensitive areas

## User Interaction Points

1. **Task Review**
   - Confirm task breakdown
   - Validate sequencing
   - Check completeness

2. **Risk Assessment**
   - Review potential impacts
   - Confirm rollback approach
   - Set success criteria

## Critical Elements

- Include debug patterns
- Add performance checks
- Note security concerns
- Document assumptions

## Auto-Save Task PRP

**CRITICAL: After generating the complete task document, you MUST automatically save it using the Write tool.**

1. **Generate filename**: Create a descriptive filename based on the task (e.g., "update-auth-middleware", "add-logging-system")
2. **Use Write tool**: Save the complete task content to `PRPs/{task-name}-task-{YYYY-MM-DD}.md`
3. **Confirm save**: Display success message with the exact file path
4. **Next steps**: Inform user they can review the task PRP and execute it when ready

**Do NOT just display the task content - you MUST save it to a file.**

## Quality Checklist

- [ ] All changes identified
- [ ] Dependencies mapped
- [ ] Each task has validation
- [ ] Rollback steps included
- [ ] Debug strategies provided
- [ ] Performance impact noted
- [ ] Security checked
- [ ] No missing edge cases

Remember: Small, focused changes with immediate validation.
