# Create PLANNING PRP (Advanced)

Transform rough ideas into comprehensive PRDs with rich visual documentation.

## Idea: $ARGUMENTS

## Discovery Process

1. **Concept Expansion**
   - Break down the core idea
   - Define success criteria
   - Map to business goals if provided

2. **Context7 Documentation & Research**
   - **Auto-detect technologies**: Analyze the project idea to identify ANY frameworks/libraries needed (Astro, React, Laravel, Sanity, etc.)
   - **Universal framework support**: Works with any technology stack combination
   - **Resolve library IDs**: Use mcp__context7__resolve-library-id for each identified technology
   - **Fetch architectural docs**: Use mcp__context7__get-library-docs focusing on architecture, best practices, and integration patterns
   - **Include in planning**: Integrate documentation into technical architecture and implementation sections

3. **Market & Technical Research**
   - Do deep web search for the following:
     - Market analysis
     - Competitor analysis
     - Technical feasibility study (enhanced with Context7 docs)
     - Best practice examples
     - Integration possibilities

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

## Auto-Save Planning PRP

**CRITICAL: After generating the complete planning document, you MUST automatically save it using the Write tool.**

1. **Generate filename**: Create a descriptive filename based on the project (e.g., "compliance-system-planning", "ecommerce-platform-planning")
2. **Use Write tool**: Save the complete planning content to `PRPs/{project-name}-planning-{YYYY-MM-DD}.md`
3. **Confirm save**: Display success message with the exact file path
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