# Create SPEC PRP (Advanced)

Generate a comprehensive specification-driven PRP with clear transformation goals.

## Specification: $ARGUMENTS

## Analysis Process

1. **Current State Assessment**
   - Map existing implementation
   - Identify pain points
   - Document technical debt
   - Note integration points

2. **Desired State Research with Context7**
   - **Auto-detect technologies**: Identify ANY frameworks/libraries involved in the specification (Astro, React, Laravel, Sanity, etc.)
   - **Universal migration support**: Works with any technology upgrade or migration scenario
   - **Resolve library IDs**: Use mcp__context7__resolve-library-id for detected technologies
   - **Fetch migration docs**: Use mcp__context7__get-library-docs focusing on migration, best practices, and upgrade patterns
   - **Include in spec**: Integrate current documentation into implementation strategy
   - Best practices for target state (enhanced with Context7 docs)
   - Implementation examples
   - Migration strategies
   - Risk assessment
   - Dependency mapping

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

## Auto-Save Specification PRP

**CRITICAL: After generating the complete specification document, you MUST automatically save it using the Write tool.**

1. **Generate filename**: Create a descriptive filename based on the specification (e.g., "database-migration-spec", "api-refactor-spec")
2. **Use Write tool**: Save the complete specification content to `PRPs/{spec-name}-spec-{YYYY-MM-DD}.md`
3. **Confirm save**: Display success message with the exact file path
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
