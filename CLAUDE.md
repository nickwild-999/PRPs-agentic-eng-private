# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Nature

This is a **PRP (Product Requirement Prompt) Framework** repository, not a traditional software project. The core concept: **"PRP = PRD + curated codebase intelligence + agent/runbook"** - designed to enable AI agents to ship production-ready code on the first pass.

## Core Architecture

### Command-Driven System

- **28+ pre-configured Claude Code commands** in `.claude/commands/`
- Commands organized by function:
  - `PRPs/` - PRP creation and execution workflows
  - `development/` - Core development utilities (prime-core, onboarding, debug)
  - `code-quality/` - Review and refactoring commands
  - `rapid-development/experimental/` - Parallel PRP creation and hackathon tools
  - `git-operations/` - Conflict resolution and smart git operations

### Template-Based Methodology

- **PRP Templates** in `PRPs/templates/` follow structured format with validation loops
- **Context-Rich Approach**: Every PRP must include comprehensive documentation, examples, and gotchas
- **Validation-First Design**: Each PRP contains executable validation gates (syntax, tests, integration)

### AI Documentation Curation

- `PRPs/ai_docs/` contains curated Claude Code documentation for context injection
- `claude_md_files/` provides framework-specific CLAUDE.md examples

## Development Commands

### PRP Execution

**Primary Method (Direct Claude Code):**
```bash
# Execute saved PRPs directly
/execute-base-prp PRPs/my-feature-2025-01-01.md
# or
claude -f PRPs/my-feature-2025-01-01.md
```

**Alternative Method (Python Runner - Optional):**
```bash
# Interactive mode (if Python runner is preferred)
uv run PRPs/scripts/prp_runner.py --prp [prp-name] --interactive

# JSON output mode
uv run PRPs/scripts/prp_runner.py --prp [prp-name] --output-format json
```

### Key Claude Commands

**PRP Creation (Auto-saves to PRPs/ directory with Context7 integration):**
- `/prp-base-create` - Generate comprehensive PRPs with Context7 docs, research and auto-save
- `/prp-planning-create` - Create project planning PRPs with Context7 architectural guidance and auto-save
- `/prp-spec-create` - Generate specification PRPs with Context7 migration docs and auto-save
- `/prp-task-create` - Create focused task PRPs with Context7 task-specific docs and auto-save

**PRP Execution:**
- `/execute-base-prp` - Execute saved PRPs against codebase
- `/prp-planning-create` - Create planning documents with diagrams
- `/prime-core` - Prime Claude with project context
- `/review-staged-unstaged` - Review git changes using PRP methodology

## Critical Success Patterns

### The PRP Methodology with Context7 Integration

1. **Context is King**: Include ALL necessary documentation, examples, and caveats (now enhanced with live Context7 docs)
2. **Auto-Documentation**: Framework docs automatically pulled from Context7 during PRP creation
3. **Validation Loops**: Provide executable tests/lints the AI can run and fix
4. **Information Dense**: Use keywords and patterns from the codebase
5. **Progressive Success**: Start simple, validate, then enhance

### PRP Structure Requirements

- **Goal**: Specific end state and desires
- **Why**: Business value and user impact
- **What**: User-visible behavior and technical requirements
- **All Needed Context**: Context7 docs (auto-fetched), documentation URLs, code examples, gotchas, patterns
- **Implementation Blueprint**: Pseudocode with critical details and task lists
- **Validation Loop**: Executable commands for syntax, tests, integration

### Validation Gates (Must be Executable - Adapt to Your Stack)

```bash
# Level 1: Syntax & Style (Examples by technology)
# Laravel:
vendor/bin/pint && vendor/bin/phpstan analyse

# Node.js/React:
npm run lint && npm run type-check

# Python (if applicable):
ruff check --fix && mypy .

# Level 2: Unit Tests
# Laravel:
php artisan test --coverage

# Node.js/React:
npm run test

# Python:
pytest tests/ -v

# Level 3: Integration (Example patterns)
# API Testing:
curl -X POST http://localhost:8000/api/endpoint -H "Content-Type: application/json" -d '{...}'

# Level 4: Deployment & Advanced Validation
# MCP servers, load testing, or other creative validation methods
```

## Anti-Patterns to Avoid

- L Don't create minimal context prompts - context is everything - the PRP must be comprehensive and self-contained, reference relevant documentation and examples.
- L Don't skip validation steps - they're critical for one-pass success - The better The AI is at running the validation loop, the more likely it is to succeed.
- L Don't ignore the structured PRP format - it's battle-tested
- L Don't create new patterns when existing templates work
- L Don't hardcode values that should be config
- L Don't catch all exceptions - be specific

## Working with This Framework

### When Creating new PRPs

1. **Context Process**: New PRPs must consist of context sections, Context is King!
2.

### When Executing PRPs

1. **Load PRP**: Read and understand all context and requirements
2. **ULTRATHINK**: Create comprehensive plan, break down into todos, use subagents, batch tool etc check prps/ai_docs/
3. **Execute**: Implement following the blueprint
4. **Validate**: Run each validation command, fix failures
5. **Complete**: Ensure all checklist items done

### Command Usage

- Read the .claude/commands directory
- Access via `/` prefix in Claude Code
- Commands are self-documenting with argument placeholders
- Use parallel creation commands for rapid development
- Leverage existing review and refactoring commands

## Project Structure Understanding

```
PRPs-agentic-eng/
.claude/
  commands/           # 28+ Claude Code commands
  settings.local.json # Tool permissions
PRPs/
  templates/          # PRP templates with validation
  scripts/           # PRP runner and utilities (optional Python tools)
  ai_docs/           # Curated Claude Code documentation
   *.md               # Active and example PRPs
 claude_md_files/        # Framework-specific CLAUDE.md examples
 pyproject.toml         # Framework package configuration (optional)
```

Remember: This framework is about **one-pass implementation success through comprehensive context and validation**. Every PRP should contain the exact context for an AI agent to successfully implement working code in a single pass.
