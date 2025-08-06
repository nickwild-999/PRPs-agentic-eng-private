> Initialize PRP Framework in a new project

# Initialize PRP Framework

This command sets up the PRP (Product Requirement Prompt) framework in your current project directory.

## What this command does:

1. **Detect your tech stack** by checking for:
   - `package.json` (Node.js/React/Next.js/Astro)
   - `composer.json` (Laravel/PHP)
   - `pyproject.toml` or `requirements.txt` (Python)
   - Other framework indicators

2. **Copy framework structure**:
   - `.claude/commands/` - All PRP commands
   - `PRPs/` directory with templates and scripts
   - `PRPs/ai_docs/` - Claude Code documentation

3. **Install appropriate CLAUDE.md**:
   - Detect your framework automatically
   - Copy the matching CLAUDE.md from `claude_md_files/`
   - Fallback to generic CLAUDE.md if framework not detected

4. **Set up validation commands** based on detected stack

## Implementation Steps:

1. First, analyze the current directory to detect the tech stack
2. Copy the core PRP framework files from the source repository
3. Select and customize the appropriate CLAUDE.md template
4. Create initial PRPs directory structure
5. Confirm successful setup

## Source Repository Path:
Use the environment variable `PRP_FRAMEWORK_PATH` or default to:
`/Users/nickwild/Programming/Automation/Agency/Claude Tools/PRPs-agentic-eng`

## Usage:
Simply run `/init` in your new project directory after installing your base framework.

The command will detect your stack and set up everything needed for the PRP workflow.