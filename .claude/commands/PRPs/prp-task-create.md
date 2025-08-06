# Create TASK PRP (Advanced)

Generate a comprehensive task list for focused changes with validation.

## Task: $ARGUMENTS

## Automatic Subagent Task Analysis

**IMPORTANT**: This command now uses specialized subagents for comprehensive task analysis and validation.

### Automatic Subagent Usage
- **Codebase Pattern Analyst**: Scope analysis and dependency mapping
- **Context7 Documentation Agent**: Task-specific technology documentation
- **PRP Research Specialist**: Similar change pattern research
- **PRP Quality Validator**: Task specification quality validation

### Analysis Process (Enhanced by Subagents)

1. **Comprehensive Scope Analysis** (Codebase Pattern Analyst)
   **CRITICAL**: When delegating, provide:
   - **Complete task description**: "$ARGUMENTS" with specific change requirements
   - **Current system context**: Existing implementation and architecture
   - **Change boundaries**: What should and shouldn't be modified
   - **Impact assessment**: Side effects and integration considerations
   
   The analyst will:
   - Identify ALL affected files and dependencies systematically
   - Map change impact across the codebase
   - Check for potential side effects and conflicts
   - Note current test coverage for affected areas
   - Document rollback requirements and safety constraints

2. **Task-Specific Documentation** (Context7 Documentation Agent)
   - Auto-detects technologies involved in the specific task
   - Fetches focused documentation for the exact functionality being modified
   - Provides method-specific API references and patterns
   - Includes best practices for the type of change being made

3. **Change Pattern Research** (PRP Research Specialist)
   Conducts focused research on:
   - Similar changes in project history and patterns
   - Conventions and patterns to follow for this change type
   - Helper functions and utilities available for reuse
   - Test patterns and validation approaches for similar changes
   - Risk mitigation strategies for this type of modification

4. **User Clarification**
   - Confirm change scope and boundaries
   - Verify acceptance criteria and success metrics
   - Check deployment considerations and timing
   - Identify potential blockers or dependencies

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

## Quality Validation & Auto-Save

### Task Specification Quality Validation (PRP Quality Validator)
Before saving, the PRP Quality Validator subagent will automatically validate:
- **Scope Completeness** (target: 8+/10): All affected files and dependencies identified
- **Task Clarity** (target: 8+/10): Each task action clear and executable
- **Validation Coverage** (target: 8+/10): Comprehensive validation and rollback strategies
- **Risk Management** (target: 8+/10): Side effects identified with mitigation strategies

**CRITICAL**: When delegating to subagents, you MUST instruct them to save the final document:
- "After completing the task analysis and validation, you MUST save the complete task PRP using the Write tool"
- "Generate descriptive filename and save to PRPs/{task-name}-task-{YYYY-MM-DD}.md"
- "Do NOT just display content - you MUST save to file and confirm the save"

### Auto-Save Task PRP

**CRITICAL: After quality validation passes, automatically save using the Write tool.**

1. **Generate filename**: Create a descriptive filename based on the task (e.g., "update-auth-middleware", "add-logging-system")
2. **Use Write tool**: Save the complete task content to `PRPs/{task-name}-task-{YYYY-MM-DD}.md`
3. **Confirm save**: Display success message with exact file path and quality scores
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
