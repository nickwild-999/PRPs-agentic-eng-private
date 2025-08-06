# Create BASE PRP

## Feature: $ARGUMENTS

Generate a complete PRP for feature implementation with deep and thorough research. Ensure rich context is passed to the AI through the PRP to enable one pass implementation success through self-validation and iterative refinement.

The AI agent only gets the context you are appending to the PRP and its own training data. Assume the AI agent has access to the codebase and the same knowledge cutoff as you, so its important that your research findings are included or referenced in the PRP. The Agent has Websearch capabilities, so pass urls to documentation and examples.

## Automatic Subagent Delegation

**IMPORTANT**: This command now uses specialized subagents for comprehensive research. Claude Code will automatically delegate tasks to appropriate subagents:

### Automatic Subagent Usage
- **PRP Research Specialist**: Automatically handles comprehensive research coordination
- **Context7 Documentation Agent**: Automatically detects and fetches current documentation
- **Codebase Pattern Analyst**: Automatically analyzes existing implementations and patterns
- **PRP Quality Validator**: Automatically validates PRP quality before completion

### Research Process (Handled by Subagents)

1. **Comprehensive Research Coordination** (PRP Research Specialist)
   **CRITICAL**: When delegating to the PRP Research Specialist, you MUST provide:
   - **Complete feature request**: "$ARGUMENTS" with full user requirements and context
   - **Project context**: Current technology stack, architecture, and development environment
   - **Business context**: Why this feature is needed and success criteria
   - **Quality requirements**: Performance, security, testing, and compliance needs
   - **Existing research**: Any previous analysis or related implementations
   
   The specialist will then:
   - Conduct parallel research across all dimensions simultaneously
   - Coordinate codebase analysis, Context7 integration, external research, and documentation
   - Synthesize findings into structured, PRP-ready context

2. **Context7 Documentation Integration** (Context7 Documentation Agent)
   - **Auto-detects technologies**: Analyzes feature request for ANY frameworks/libraries
   - **Universal support**: Frontend (Astro, React, Vue), backend (Laravel, Node.js), CMS (Sanity, Strapi), databases
   - **Fetches current docs**: Uses Context7 for up-to-date documentation with topic focus
   - **Integrates seamlessly**: Structures documentation for immediate PRP inclusion

3. **Codebase Pattern Analysis** (Codebase Pattern Analyst)
   - Identifies similar feature implementations and reusable patterns
   - Documents architectural patterns and code conventions to follow
   - Analyzes testing patterns and validation approaches
   - Provides specific file references and implementation guidance

4. **User Clarification**
   - Ask for clarification if needed before subagent delegation begins

## PRP Generation

Using PRPs/templates/prp_base.md as template:

### Critical Context at minimum to Include and pass to the AI agent as part of the PRP

- **Context7 Documentation**: Current framework/library docs automatically fetched and integrated
- **Documentation**: URLs with specific sections
- **Code Examples**: Real snippets from codebase
- **Gotchas**: Library quirks, version issues
- **Patterns**: Existing approaches to follow
- **Best Practices**: Common pitfalls found during research

### Implementation Blueprint

- Start with pseudocode showing approach
- Reference real files for patterns
- Include error handling strategy
- List tasks to be completed to fulfill the PRP in the order they should be completed, use the pattern in the PRP with information dense keywords

### Validation Gates (Must be Executable by the AI agent)

Use appropriate validation commands for the project type:

**For Laravel Projects:**
```bash
# Syntax/Style
vendor/bin/pint
vendor/bin/phpstan analyse

# Unit Tests
php artisan test --coverage
```

**For Astro Projects:**
```bash
# Syntax/Style
npm run lint
npm run type-check

# Build Tests
npm run build
npm run test
```

**For React/Node.js Projects:**
```bash
# Syntax/Style
npm run lint
npm run type-check

# Unit Tests
npm run test
```

**For Python Projects:**
```bash
# Syntax/Style
ruff check --fix
mypy .

# Unit Tests
pytest tests/ -v
```

The more validation gates the better, but make sure they are executable by the AI agent.
Include tests, appropriate linting tools, and any other relevant validation gates for the specific technology stack.

**_ CRITICAL AFTER YOU ARE DONE RESEARCHING AND EXPLORING THE CODEBASE BEFORE YOU START WRITING THE PRP _**

**_ ULTRATHINK ABOUT THE PRP AND PLAN YOUR APPROACH IN DETAILED TODOS THEN START WRITING THE PRP _**

## Quality Validation & Auto-Save

### PRP Quality Validation (PRP Quality Validator)
Before saving, the PRP Quality Validator subagent will automatically:
- Validate context richness (target: 8+/10)
- Assess implementation clarity (target: 8+/10)
- Verify validation completeness (target: 8+/10)
- Calculate one-pass success probability (target: 8+/10)
- Provide improvement recommendations if scores are below target

**CRITICAL**: When delegating to subagents, you MUST instruct them to save the final PRP:
- "After completing research, generation, and validation, you MUST save the complete PRP using the Write tool"
- "Generate descriptive filename and save to PRPs/{feature-name}-{YYYY-MM-DD}.md"
- "Do NOT just display PRP content - you MUST save to file and confirm the save with exact file path"

### Auto-Save PRP

**CRITICAL: After quality validation passes, you MUST automatically save the PRP using the Write tool.**

1. **Generate filename**: Create a descriptive filename based on the feature (e.g., "user-authentication-system", "payment-processing-module")
2. **Use Write tool**: Save the complete PRP content to `PRPs/{feature-name}-{YYYY-MM-DD}.md`
3. **Confirm save**: Display success message with the exact file path and quality scores
4. **Next steps**: Inform user they can review the PRP and execute it when ready using `/execute-base-prp`

**Do NOT just display the PRP content - you MUST save it to a file.**

## Quality Checklist

- [ ] All necessary context included
- [ ] Validation gates are executable by AI
- [ ] References existing patterns
- [ ] Clear implementation path
- [ ] Error handling documented

Score the PRP on a scale of 1-10 (confidence level to succeed in one-pass implementation using claude codes)

Remember: The goal is one-pass implementation success through comprehensive context.

**Final Step: ALWAYS use the Write tool to save the generated PRP to PRPs/{feature-name}-{date}.md and confirm the save to the user.**
