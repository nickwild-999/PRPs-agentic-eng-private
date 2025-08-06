# Execute BASE PRP

Implement a feature using the PRP file.

## PRP File: $ARGUMENTS

## Automatic Subagent Execution

**IMPORTANT**: This command now uses the PRP Implementation Coordinator subagent for systematic execution with proper validation loops and error handling.

### Automatic Delegation to PRP Implementation Coordinator

**CRITICAL**: When delegating to the PRP Implementation Coordinator, you MUST provide ALL necessary context:

#### Required Context for Implementation Subagent:
1. **Complete PRP Content**: Read and pass the entire PRP file content to the subagent
2. **Current Project State**: 
   - Current directory structure (`tree` or `ls -la` of key directories)
   - Git status and any uncommitted changes
   - Current branch and recent commits
3. **Environment Status**:
   - Dependencies installed and versions (`package.json`, `composer.json`, `requirements.txt`, etc.)
   - Build tools working (`npm run`, `composer`, `pip`, etc.)
   - Database status and connections
4. **Integration Context**:
   - Existing API endpoints and contracts
   - Database schema and relationships  
   - External service configurations
   - Performance and security requirements

#### Context Passing Protocol:
```
BEFORE delegating to PRP Implementation Coordinator:
1. Read the complete PRP file: "$ARGUMENTS"
2. Analyze current codebase state
3. Verify development environment is ready
4. Pass ALL context explicitly to the subagent
5. Include any constraints or special requirements
```

The specialized coordinator will then:

1. **Load and Analyze PRP**
   - Read and comprehensively analyze the specified PRP file
   - Understand all context, requirements, and validation gates
   - Create systematic implementation plan with TodoWrite
   - Identify dependencies and integration points

2. **Systematic Implementation**
   - Execute implementation tasks in proper dependency order
   - Follow existing codebase patterns and conventions from PRP research
   - Implement with proper error handling and logging
   - Validate each task immediately after completion

3. **Comprehensive Validation Execution**
   - **Level 1**: Syntax & Style validation with project-specific commands
   - **Level 2**: Unit testing with proper coverage requirements
   - **Level 3**: Integration testing and end-to-end validation
   - **Level 4**: Creative validation (performance, security, UX)

4. **Error Handling and Iteration**
   - Systematic error analysis and resolution
   - Apply fixes following established patterns from PRP
   - Re-validate until all quality gates pass
   - Document any implementation adjustments needed

5. **Quality Assurance and Completion**
   - Execute final validation checklist from PRP
   - Verify all requirements met per PRP specification
   - Generate comprehensive implementation report
   - Confirm one-pass implementation success

### Manual Override
If you need to handle execution manually instead of using the subagent:
- Explicitly request "manual execution without subagent"
- Follow the original step-by-step process
- Use TodoWrite for task breakdown and tracking

Note: If validation fails, use error patterns in PRP to fix and retry.
