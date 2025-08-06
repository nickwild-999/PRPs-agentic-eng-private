# Global Agents Approach for PRP Framework

## Overview

The PRP framework subagents are now installed **globally** (`~/.claude/agents/`) rather than per-project. This provides universal availability, easier maintenance, and consistent quality across all projects.

## Why Global Agents Are Better

### ✅ Advantages

1. **Universal Availability**: Work across ALL your projects automatically
2. **Single Source of Truth**: Update once, benefits everywhere
3. **No Duplication**: Don't copy agents to every project
4. **Easier Maintenance**: Manage agents in one location
5. **Team Consistency**: Same quality agents for entire team
6. **Version Control**: Can sync via dotfiles or team scripts

### ❌ Problems with Project-Level Agents (Avoided)

1. **Duplication Nightmare**: Would need to copy to every project
2. **Update Hell**: Would need to update in dozens of places
3. **Version Drift**: Different projects could have different agent versions
4. **Maintenance Overhead**: Managing across many project directories

## Global Agent Installation

### Current Installation
```bash
# PRP agents are installed globally at:
~/.claude/agents/
├── prp-research-specialist.md
├── prp-quality-validator.md  
├── context7-documentation-agent.md
├── prp-implementation-coordinator.md
└── codebase-pattern-analyst.md
```

### Verification
```bash
# Check installed agents
ls -la ~/.claude/agents/

# Test agent availability (in any project)
claude
> /agents
```

## How Global Agents Work

### Automatic Selection
Claude Code automatically uses global agents when:
- Agent descriptions match the current task type
- "Use proactively" patterns trigger automatic delegation
- Tools required are available for the task

### Priority System
```
1. Project-level agents (.claude/agents/) - HIGHEST [Not used in PRP framework]
2. User-level agents (~/.claude/agents/) - HIGH [PRP framework agents here]
3. Built-in agents - LOWEST
```

Since PRP agents are global, they have **high priority** and work across all projects.

### Technology Stack Agnostic
The global PRP agents work with **ANY** technology stack:
- **Context7 Integration**: Auto-detects and fetches docs for any technology
- **Universal Patterns**: Codebase analysis works for any language/framework
- **Quality Standards**: Consistent 8+/10 metrics regardless of tech stack

## Team Deployment Strategies

### Option 1: Dotfiles Approach
```bash
# Add to your dotfiles repository
mkdir -p ~/.dotfiles/claude/agents
cp ~/.claude/agents/*.md ~/.dotfiles/claude/agents/

# Team installation script
#!/bin/bash
mkdir -p ~/.claude/agents
cp ~/.dotfiles/claude/agents/*.md ~/.claude/agents/
```

### Option 2: Installation Script
```bash
#!/bin/bash
# install-prp-agents.sh

AGENTS_DIR="$HOME/.claude/agents"
mkdir -p "$AGENTS_DIR"

# Download or copy PRP agents
curl -o "$AGENTS_DIR/prp-research-specialist.md" "https://raw.githubusercontent.com/your-org/prp-agents/main/prp-research-specialist.md"
# ... other agents

echo "PRP agents installed globally at $AGENTS_DIR"
```

### Option 3: Symlink Approach
```bash
# Keep agents in a shared repo, symlink globally
ln -s /path/to/shared/prp-agents/* ~/.claude/agents/
```

## Maintenance and Updates

### Updating All Agents
```bash
# Update global agents (affects all projects immediately)
cd ~/.claude/agents
# Edit agent files or pull from shared repository
```

### Version Management
```bash
# Tag agent versions for rollback capability
cd ~/.claude/agents
git init
git add *.md
git commit -m "PRP agents v1.0"
git tag v1.0
```

### Testing Updates
```bash
# Test updated agents across different projects
cd ~/project1 && claude -p "test prp research specialist"
cd ~/project2 && claude -p "test context7 documentation agent"
```

## Framework Integration

### Command Updates Not Needed
Since commands reference agents by **name** (not path), they automatically use global agents:

```markdown
- **PRP Research Specialist**: Automatically handles comprehensive research
- **Context7 Documentation Agent**: Automatically detects technologies
```

The framework commands work exactly the same whether agents are local or global.

### Project Onboarding
```bash
# New project setup - no agent copying needed!
cd new-project
cp /path/to/PRPs-agentic-eng/.claude/commands/ .claude/
cp /path/to/PRPs-agentic-eng/CLAUDE.md .
cp /path/to/PRPs-agentic-eng/PRPs/ .

# Agents already available globally - ready to use!
claude
> /prp-base-create user authentication system
```

## Technology-Specific Agents

### Integration with Existing Global Agents
If you have existing technology-specific global agents:

```bash
~/.claude/agents/
├── prp-research-specialist.md          # PRP framework
├── prp-quality-validator.md            # PRP framework  
├── context7-documentation-agent.md     # PRP framework
├── prp-implementation-coordinator.md   # PRP framework
├── codebase-pattern-analyst.md         # PRP framework
├── laravel-backend-specialist.md       # Your existing
├── react-frontend-specialist.md        # Your existing
└── aws-deployment-specialist.md        # Your existing
```

### Agent Collaboration
PRP agents can delegate to your technology specialists:

```markdown
# In prp-research-specialist.md
When handling Laravel projects:
1. Delegate Laravel-specific research to laravel-backend-specialist
2. Apply PRP methodology to structure findings
3. Integrate Context7 Laravel documentation
4. Ensure 8+/10 quality metrics
```

## Benefits Realized

### Development Workflow
```bash
# Same high-quality agents everywhere
cd ~/project-laravel && claude # PRP agents available
cd ~/project-react && claude   # Same PRP agents available  
cd ~/project-python && claude  # Same PRP agents available
```

### Quality Consistency
- ✅ Same research depth across all projects
- ✅ Same quality validation standards (8+/10)
- ✅ Same Context7 integration for any tech stack
- ✅ Same implementation methodology

### Maintenance Efficiency
- ✅ Update once, improve all projects
- ✅ No version drift between projects
- ✅ Easy to add new capabilities
- ✅ Team synchronization simplified

## Migration Guide

### From Project-Level to Global (Completed)
```bash
# 1. Copy agents to global location ✅
cp .claude/agents/*.md ~/.claude/agents/

# 2. Remove local agents ✅  
rm -rf .claude/agents/

# 3. Test functionality ✅
claude
> /agents  # Should show global agents

# 4. Verify commands work ✅
> /prp-base-create test feature
```

### Team Migration
```bash
# Each team member runs:
mkdir -p ~/.claude/agents
# Install agents via chosen method (dotfiles, script, etc.)
```

## Future Enhancements

### Agent Discovery
```bash
# Script to list all available global agents
#!/bin/bash
echo "Available PRP Agents:"
ls ~/.claude/agents/ | grep -E "(prp|context7|codebase)" | sed 's/.md$//'
```

### Agent Health Check
```bash
# Verify all required agents are installed
#!/bin/bash
required_agents=("prp-research-specialist" "prp-quality-validator" "context7-documentation-agent" "prp-implementation-coordinator" "codebase-pattern-analyst")

for agent in "${required_agents[@]}"; do
  if [[ -f ~/.claude/agents/$agent.md ]]; then
    echo "✅ $agent"
  else
    echo "❌ $agent (missing)"
  fi
done
```

## Conclusion

**Global agents provide the optimal approach for the PRP framework:**

- ✅ **Universal availability** across all projects
- ✅ **Easier maintenance** and updates
- ✅ **Consistent quality** and capabilities
- ✅ **Team synchronization** simplified
- ✅ **No duplication** or version drift

The PRP framework now provides high-quality AI assistance for any project, anywhere, with minimal setup and maximum consistency.