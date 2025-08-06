# Create PLANNING PRP (Advanced)

Transform rough ideas into comprehensive PRDs with rich visual documentation.

## Idea: $ARGUMENTS

## Automatic Subagent Planning Process

**IMPORTANT**: This command now uses specialized subagents for comprehensive planning research and quality validation.

### Automatic Subagent Usage
- **PRP Research Specialist**: Comprehensive market, technical, and architectural research
- **Context7 Documentation Agent**: Technology detection and architectural documentation
- **Codebase Pattern Analyst**: Current system analysis for integration planning
- **PRP Quality Validator**: Planning document quality validation before saving

### Discovery Process (Enhanced by Subagents)

1. **Comprehensive Planning Research** (PRP Research Specialist)
   **CRITICAL**: When delegating to the specialist, provide:
   - **Complete project idea**: "$ARGUMENTS" with full vision and requirements
   - **Business context**: Goals, success metrics, target users, constraints
   - **Technical context**: Existing systems, technology preferences, integration needs
   - **Market context**: Competitive landscape, user needs, industry standards
   
   The specialist will conduct parallel research across:
   - Market analysis and competitive landscape
   - Technical feasibility with Context7 architectural guidance
   - Best practices and implementation examples
   - Integration possibilities and technology options
   - Risk assessment and mitigation strategies

2. **Technology Architecture Research** (Context7 Documentation Agent)
   - Auto-detects ALL relevant technologies for the project idea
   - Fetches current architectural documentation and best practices
   - Provides integration patterns and technology combination guidance
   - Includes migration paths and technology evolution strategies

3. **Current System Analysis** (Codebase Pattern Analyst) 
   - Analyzes existing codebase for integration patterns
   - Identifies architectural constraints and opportunities
   - Documents current technology stack and conventions
   - Maps integration points for new features

4. **User Research & Clarification**
     - Ask user for the following if not provided:
     - Target user personas?
     - Key pain points?
     - Success metrics?
     - Constraints/requirements?

## PRD Generation

Using /PRPs/templates/prp_planning_base.md:

### Visual Documentation Plan
```yaml
diagrams_needed:
  user_flows:
    - Happy path journey
    - Error scenarios
    - Edge cases
  
  architecture:
    - System components
    - Data flow
    - Integration points
  
  sequences:
    - API interactions
    - Event flows
    - State changes
  
  data_models:
    - Entity relationships
    - Schema design
    - State machines
```

### Research Integration
- **Context7 Documentation**: Current framework docs with architectural guidance
- **Market Analysis**: Include findings in PRD
- **Technical Options**: Compare approaches (informed by Context7 best practices)
- **Risk Assessment**: With mitigation strategies
- **Success Metrics**: Specific, measurable

### User Story Development
```markdown
## Epic: [High-level feature]

### Story 1: [User need]
**As a** [user type]
**I want** [capability]
**So that** [benefit]

**Acceptance Criteria:**
- [ ] Specific behavior
- [ ] Edge case handling
- [ ] Performance requirement

**Technical Notes:**
- Implementation approach
- API implications
- Data requirements
```

### Implementation Strategy
- Phases with dependencies (no dates)
- Priority ordering
- MVP vs enhanced features
- Technical prerequisites

## User Interaction Points

1. **Idea Validation**
   - Confirm understanding
   - Clarify ambiguities
   - Set boundaries

2. **Research Review**
   - Share findings
   - Validate assumptions
   - Adjust direction

3. **PRD Draft Review**
   - Architecture approval
   - Risk acknowledgment
   - Success metric agreement

## Diagram Guidelines
- Use Mermaid for all diagrams
- Include legends where needed
- Show error paths
- Annotate complex flows

## Output Structure
```markdown
1. Executive Summary
2. Problem & Solution
3. User Stories (with diagrams)
4. Technical Architecture (with diagrams)
5. API Specifications
6. Data Models
7. Implementation Phases
8. Risks & Mitigations
9. Success Metrics
10. Appendices
```

## Quality Validation & Auto-Save

### Planning Document Quality Validation (PRP Quality Validator)
Before saving, the PRP Quality Validator subagent will automatically validate:
- **Planning Completeness** (target: 8+/10): All sections comprehensive and actionable
- **Research Quality** (target: 8+/10): Market, technical, and competitive analysis thorough
- **Architecture Clarity** (target: 8+/10): Technical approach clear and well-documented
- **Implementation Readiness** (target: 8+/10): Ready for breakdown into implementation PRPs

**CRITICAL**: When delegating to subagents, you MUST instruct them to save the final planning document:
- "After completing planning research and validation, you MUST save the complete planning PRP using the Write tool"
- "Generate descriptive filename and save to PRPs/{project-name}-planning-{YYYY-MM-DD}.md"
- "Do NOT just display planning content - you MUST save to file and confirm the save with exact file path"

### Auto-Save Planning PRP

**CRITICAL: After quality validation passes, automatically save using the Write tool.**

1. **Generate filename**: Create a descriptive filename based on the project (e.g., "compliance-system-planning", "ecommerce-platform-planning")
2. **Use Write tool**: Save the complete planning content to `PRPs/{project-name}-planning-{YYYY-MM-DD}.md`
3. **Confirm save**: Display success message with exact file path and quality scores
4. **Next steps**: Inform user they can review the planning PRP and create implementation PRPs when ready

**Do NOT just display the planning content - you MUST save it to a file.**

## Quality Checklist
- [ ] Problem clearly articulated
- [ ] Solution addresses problem
- [ ] All user flows diagrammed
- [ ] Wireframes included if needed
- [ ] Architecture visualized
- [ ] APIs fully specified with examples
- [ ] Data models included
- [ ] Dependencies identified
- [ ] Risks identified and mitigated
- [ ] Success metrics measurable
- [ ] Implementation phases logical
- [ ] Ready for implementation PRP

Remember: Great PRDs prevent implementation confusion.