# Create SPEC PRP (Advanced)

Generate a comprehensive specification-driven PRP with clear transformation goals.

## Specification: $ARGUMENTS

## Automatic Subagent Specification Process

**IMPORTANT**: This command now uses specialized subagents for comprehensive specification analysis and validation.

### Automatic Subagent Usage
- **PRP Research Specialist**: Comprehensive migration and transformation research
- **Context7 Documentation Agent**: Technology upgrade and migration documentation
- **Codebase Pattern Analyst**: Current state analysis and transformation planning
- **PRP Quality Validator**: Specification quality validation before saving

### Analysis Process (Enhanced by Subagents)

1. **Current State Analysis** (Codebase Pattern Analyst)
   **CRITICAL**: When delegating, provide:
   - **Specification request**: "$ARGUMENTS" with complete transformation goals
   - **Current system context**: Existing implementation and architecture
   - **Pain points**: Known issues and technical debt to address
   - **Integration constraints**: Existing systems that must be maintained
   
   The analyst will:
   - Map existing implementation comprehensively
   - Identify pain points and technical debt systematically
   - Document current integration points and dependencies
   - Analyze transformation complexity and risks

2. **Migration & Transformation Research** (PRP Research Specialist)
   Conducts parallel research across:
   - Best practices for transformation scenarios
   - Migration strategies and implementation examples
   - Risk assessment and mitigation approaches
   - Dependency mapping and sequencing strategies
   - Performance and compatibility considerations

3. **Technology Upgrade Documentation** (Context7 Documentation Agent)
   - Auto-detects ALL technologies involved in the specification
   - Fetches current migration and upgrade documentation
   - Provides version-specific migration guides and breaking changes
   - Includes best practices for technology transitions and integrations

3. **User Clarification**
   - Confirm transformation goals
   - Priority of objectives
   - Acceptable trade-offs

## PRP Generation

Using /PRPs/templates/prp_spec.md:

### State Documentation

```yaml
current_state:
  files: [list affected files]
  behavior: [how it works now]
  issues: [specific problems]

desired_state:
  files: [expected structure]
  behavior: [target functionality]
  benefits: [improvements gained]
```

### Hierarchical Objectives

1. **High-Level**: Overall transformation goal
2. **Mid-Level**: Major milestones
3. **Low-Level**: Specific tasks with validation

### Task Specification with information dense keywords

#### Information dense keywords:

- MIRROR: Mirror the state of existing code to be mirrored to another use case
- COPY: Copy the state of existing code to be copied to another use case
- ADD: Add new code to the codebase
- MODIFY: Modify existing code
- DELETE: Delete existing code
- RENAME: Rename existing code
- MOVE: Move existing code
- REPLACE: Replace existing code
- CREATE: Create new code

#### Example:

```yaml
task_name:
  action: MODIFY/CREATE
  file: path/to/file
  changes: |
    - Specific modifications
    - Implementation details
    - With clear markers
  validation:
    - command: "test command"
    - expect: "success criteria"
```

### Implementation Strategy

- Identify dependencies
- Order tasks by priority and implementation order and dependencies logic
- Include rollback plans
- Progressive enhancement

## User Interaction Points

1. **Objective Validation**
   - Review hierarchical breakdown
   - Confirm priorities
   - Identify missing pieces

2. **Risk Review**
   - Document identified risks
   - Find mitigations
   - Set go/no-go criteria

## Context Requirements

- Context7 documentation for involved technologies
- Current implementation details
- Target architecture examples
- Migration best practices (from Context7 and web research)
- Testing strategies

## Quality Validation & Auto-Save

### Specification Quality Validation (PRP Quality Validator)
Before saving, the PRP Quality Validator subagent will automatically validate:
- **Current State Documentation** (target: 8+/10): Existing system thoroughly analyzed
- **Transformation Clarity** (target: 8+/10): Desired state and path clearly defined
- **Task Specification** (target: 8+/10): Implementation tasks detailed and executable
- **Risk Management** (target: 8+/10): Risks identified with mitigation strategies

**CRITICAL**: When delegating to subagents, you MUST instruct them to save the final specification:
- "After completing specification analysis and validation, you MUST save the complete specification PRP using the Write tool"
- "Generate descriptive filename and save to PRPs/{spec-name}-spec-{YYYY-MM-DD}.md"
- "Do NOT just display specification content - you MUST save to file and confirm the save with exact file path"

### Auto-Save Specification PRP

**CRITICAL: After quality validation passes, automatically save using the Write tool.**

1. **Generate filename**: Create a descriptive filename based on the specification (e.g., "database-migration-spec", "api-refactor-spec")
2. **Use Write tool**: Save the complete specification content to `PRPs/{spec-name}-spec-{YYYY-MM-DD}.md`
3. **Confirm save**: Display success message with exact file path and quality scores
4. **Next steps**: Inform user they can review the specification PRP and execute it when ready

**Do NOT just display the specification content - you MUST save it to a file.**

## Quality Checklist

- [ ] Current state fully documented
- [ ] Desired state clearly defined
- [ ] All objectives measurable
- [ ] Tasks ordered by dependency
- [ ] Each task has validation that AI can run
- [ ] Risks identified with mitigations
- [ ] Rollback strategy included
- [ ] Integration points noted

Remember: Focus on the transformation journey, not just the destination.
