# Execute SPEC PRP

Implement a specification using an existing SPEC PRP.

## PRP File: $ARGUMENTS

## Automatic Subagent Execution

**IMPORTANT**: This command now uses the PRP Implementation Coordinator subagent for systematic specification execution with transformation validation.

### Automatic Delegation to PRP Implementation Coordinator

**CRITICAL**: When delegating to the coordinator, you MUST provide ALL necessary context:

#### Required Context for Specification Execution:
1. **Complete Specification Content**: Read and pass the entire SPEC PRP file content
2. **Current State Documentation**: 
   - Current system implementation and architecture
   - Known pain points and technical debt
   - Existing integration points and dependencies
3. **Transformation Goals**:
   - Desired end state and success criteria
   - Task dependencies and execution order
   - Validation gates for each transformation step
4. **Environment and Constraints**:
   - Development environment status
   - Integration testing requirements
   - Rollback procedures and safety nets

#### Context Passing Protocol for Specifications:
```
BEFORE delegating to PRP Implementation Coordinator:
1. Read the complete SPEC PRP file: "$ARGUMENTS"
2. Analyze current system state and validate against spec
3. Understand transformation goals and task dependencies
4. Verify development environment ready for changes
5. Pass ALL context explicitly including transformation strategy
6. Include rollback plans and safety considerations
```

The specialized coordinator will then:

1. **Load and Analyze Specification**
   - Understand current state and desired transformation
   - Map task dependencies and execution sequence
   - Validate transformation strategy and approach

2. **Systematic Transformation Execution**
   - Execute tasks in proper dependency order
   - Validate each transformation step immediately
   - Apply rollback procedures if transformation fails
   - Monitor system integrity throughout process

3. **Comprehensive Transformation Validation**
   - Verify desired state achieved per specification
   - Run all validation gates for each transformation
   - Test integration points and system functionality
   - Confirm transformation meets all success criteria

### Manual Override
If you need to handle specification execution manually:
- Explicitly request "manual execution without subagent"
- Follow original step-by-step transformation process
- Use TodoWrite for transformation task breakdown and tracking