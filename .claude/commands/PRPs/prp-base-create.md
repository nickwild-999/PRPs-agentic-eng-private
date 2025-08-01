# Create BASE PRP

## Feature: $ARGUMENTS

Generate a complete PRP for feature implementation with deep and thorough research. Ensure rich context is passed to the AI through the PRP to enable one pass implementation success through self-validation and iterative refinement.

The AI agent only gets the context you are appending to the PRP and its own training data. Assume the AI agent has access to the codebase and the same knowledge cutoff as you, so its important that your research findings are included or referenced in the PRP. The Agent has Websearch capabilities, so pass urls to documentation and examples.

## Research Process

> During the research process, create clear tasks and spawn as many agents and subagents as needed using the batch tools. The deeper research we do here the better the PRP will be. we optminize for chance of success and not for speed.

1. **Codebase Analysis in depth**
   - Create clear todos and spawn subagents to search the codebase for similar features/patterns Think hard and plan your approach
   - Identify all the necessary files to reference in the PRP
   - Note all existing conventions to follow
   - Check existing test patterns for validation approach
   - Use the batch tools to spawn subagents to search the codebase for similar features/patterns

2. **Context7 Documentation Integration**
   - **Auto-detect technologies**: Analyze the feature request to identify ANY frameworks/libraries (Astro, React, Laravel, Sanity, etc.)
   - **Universal support**: Works with frontend (Astro, React, Vue), backend (Laravel, Node.js), CMS (Sanity, Strapi), databases, and more
   - **Resolve library IDs**: Use mcp__context7__resolve-library-id for each detected technology
   - **Fetch current docs**: Use mcp__context7__get-library-docs with relevant topics for comprehensive documentation
   - **Include in PRP**: Integrate fetched documentation directly into the "All Needed Context" section

3. **External Research at scale**
   - Create clear todos and spawn with instructions subagents to do deep research for similar features/patterns online and include urls to documentation and examples
   - Library documentation (include specific URLs + Context7 docs already fetched)
   - For critical pieces of documentation add a .md file to PRPs/ai_docs and reference it in the PRP with clear reasoning and instructions
   - Implementation examples (GitHub/StackOverflow/blogs)
   - Best practices and common pitfalls found during research
   - Use the batch tools to spawn subagents to search for similar features/patterns online and include urls to documentation and examples

4. **User Clarification**
   - Ask for clarification if you need it

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

## Auto-Save PRP

**CRITICAL: After generating the complete PRP content, you MUST automatically save it using the Write tool.**

1. **Generate filename**: Create a descriptive filename based on the feature (e.g., "user-authentication-system", "payment-processing-module")
2. **Use Write tool**: Save the complete PRP content to `PRPs/{feature-name}-{YYYY-MM-DD}.md`
3. **Confirm save**: Display success message with the exact file path
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
