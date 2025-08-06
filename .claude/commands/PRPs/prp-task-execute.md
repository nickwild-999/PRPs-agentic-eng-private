# Execute TASK PRP

Run through a task list from an existing TASK PRP.

## PRP File: $ARGUMENTS

## Automatic Subagent Task Execution

**IMPORTANT**: This command now uses the PRP Implementation Coordinator subagent for systematic task execution with focused validation.

### Automatic Delegation to PRP Implementation Coordinator

**CRITICAL**: When delegating to the coordinator, you MUST provide ALL necessary context:

#### Required Context for Task Execution:
1. **Complete Task PRP Content**: Read and pass the entire task PRP file content
2. **Task Scope and Boundaries**: 
   - Specific files and functions to be modified
   - Change boundaries and what should NOT be touched
   - Dependencies and integration points affected
3. **Validation Strategy**:
   - Task-specific validation commands and expected outcomes
   - Rollback procedures for each task step
   - Performance and security validation requirements
4. **Current System State**:
   - Current codebase state and git status
   - Environment configuration and dependencies
   - Test coverage and existing validation setup

#### Context Passing Protocol for Tasks:
```
BEFORE delegating to PRP Implementation Coordinator:
1. Read the complete TASK PRP file: "$ARGUMENTS"
2. Analyze current system state for the specific changes
3. Understand task boundaries and validation requirements
4. Verify development environment ready for focused changes
5. Pass ALL context explicitly including task sequence and validation
6. Include rollback procedures and safety considerations for each task
```

**CRITICAL**: When delegating, you MUST instruct the coordinator:
- "Execute each task sequentially with immediate validation after each step"
- "Follow the exact ACTION, VALIDATE, IF_FAIL, ROLLBACK sequence for each task"
- "Do NOT proceed to next task until current task validation passes"
- "Generate task execution report with validation results for each step"

The specialized coordinator will then:

1. **Load and Analyze Task List**
   - Understand each task action and validation requirement
   - Map task dependencies and execution sequence
   - Prepare rollback procedures for each step

2. **Sequential Task Execution**
   - Execute each ACTION with precise scope control
   - Run VALIDATE immediately after each change
   - Apply IF_FAIL procedures systematically if validation fails
   - Execute ROLLBACK if task cannot be completed safely

3. **Comprehensive Task Validation**
   - Verify each task completed successfully per specification
   - Run validation gates after task groups
   - Test integration points and system functionality
   - Confirm no regressions introduced by changes

### Manual Override
If you need to handle task execution manually:
- Explicitly request "manual task execution without subagent"
- Follow original sequential task execution process
- Use TodoWrite for individual task tracking and validation
