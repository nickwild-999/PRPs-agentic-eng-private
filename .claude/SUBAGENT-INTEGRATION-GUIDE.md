# Subagent Integration Guide for PRP Framework

## Overview

The PRP framework now includes 5 specialized subagents that automatically enhance your existing workflow. These subagents work seamlessly with Claude Code's automatic delegation system to provide:

- **Comprehensive research** coordination
- **Quality validation** against 8+ metric standards  
- **Systematic implementation** with proper validation loops
- **Context7 documentation** integration for ANY technology stack
- **Codebase pattern analysis** for consistency and reuse

## Subagent Specifications

### 1. PRP Research Specialist (`prp-research-specialist`)
**Purpose**: Comprehensive parallel research coordination for PRP creation
**Auto-triggers on**: Any PRP creation command, research requests
**Tools**: Task, WebFetch, Grep, Glob, Read, Context7 tools
**Key Features**:
- Coordinates 4 research streams simultaneously
- Integrates Context7 documentation automatically
- Synthesizes findings into PRP-ready format
- Ensures 8+ quality scores across all research dimensions

### 2. PRP Quality Validator (`prp-quality-validator`)
**Purpose**: Validates PRP quality against comprehensive metrics before saving
**Auto-triggers on**: After PRP generation, before file saving
**Tools**: Read, Bash, Grep, Glob
**Key Features**:
- Context Richness assessment (target: 8+/10)
- Implementation Clarity validation (target: 8+/10)
- Validation Completeness verification (target: 8+/10)
- One-Pass Success Probability calculation (target: 8+/10)
- Actionable improvement recommendations

### 3. Context7 Documentation Agent (`context7-documentation-agent`)
**Purpose**: Automatic technology detection and current documentation integration
**Auto-triggers on**: Any technology mention in requests
**Tools**: Context7 MCP tools, WebFetch, Read
**Key Features**:
- Auto-detects ANY frameworks (Astro, React, Laravel, Sanity, etc.)
- Fetches current documentation with topic-specific focus
- Supports universal tech stacks (frontend, backend, CMS, databases)
- Provides fallback documentation for unsupported technologies

### 4. PRP Implementation Coordinator (`prp-implementation-coordinator`)
**Purpose**: Systematic PRP execution with validation loops and error handling
**Auto-triggers on**: PRP execution commands
**Tools**: All tools (Read, Edit, MultiEdit, Write, Bash, etc.)
**Key Features**:
- Loads and analyzes complete PRP context
- Creates systematic implementation plan with TodoWrite
- Executes with 4-level validation (syntax, unit, integration, creative)
- Handles errors systematically with pattern-based fixes
- Generates comprehensive implementation reports

### 5. Codebase Pattern Analyst (`codebase-pattern-analyst`)
**Purpose**: Discovers existing implementations and architectural patterns
**Auto-triggers on**: Before implementation, during research phase
**Tools**: Grep, Glob, Read, Task, Bash
**Key Features**:
- Identifies similar feature implementations
- Documents architectural patterns and conventions
- Analyzes testing patterns and validation approaches
- Provides specific file references and reusable components

## How Subagents Work with Existing Commands

### Enhanced PRP Creation Commands

#### `/prp-base-create` 
Now automatically uses:
1. **PRP Research Specialist** → Comprehensive parallel research
2. **Context7 Documentation Agent** → Technology detection and docs
3. **Codebase Pattern Analyst** → Pattern analysis and conventions
4. **PRP Quality Validator** → Quality validation before saving

#### `/execute-base-prp`
Now automatically uses:
1. **PRP Implementation Coordinator** → Systematic execution
2. **Codebase Pattern Analyst** → Pattern validation during implementation
3. **PRP Quality Validator** → Validation gate execution

#### `/create-base-prp-parallel`
Enhanced with:
1. **PRP Research Specialist** → Parallel research coordination
2. **All supporting subagents** → Integrated research enhancement

### Automatic Delegation

Claude Code automatically uses appropriate subagents based on:
- **Task descriptions** in your requests
- **Subagent descriptions** with "use proactively" patterns
- **Current context** and available tools
- **Request types** (research, creation, execution, validation)

### Manual Subagent Usage

You can explicitly request specific subagents:
```
> Use the prp-research-specialist to research authentication patterns
> Have the context7-documentation-agent fetch Laravel docs
> Ask the prp-quality-validator to check this PRP
```

## Benefits of Subagent Integration

### 1. Automatic Context Preservation
- Each subagent operates in its own context window
- Main conversation stays focused on high-level objectives
- No context pollution from detailed research tasks

### 2. Specialized Expertise
- Each subagent optimized for specific task types
- Higher success rates through specialized system prompts
- Consistent quality standards across all PRPs

### 3. Seamless Integration
- Works with existing command structure
- No workflow changes required
- Enhances current methodology without breaking changes

### 4. Enhanced Quality Standards
- Systematic 8+ quality score validation
- Comprehensive research across all dimensions
- Proper validation loops with error handling
- One-pass implementation success optimization

## Usage Examples

### Creating a PRP with Automatic Subagent Usage
```bash
# Standard command - subagents work automatically
/prp-base-create user authentication with Laravel Sanctum

# What happens automatically:
# 1. PRP Research Specialist coordinates comprehensive research
# 2. Context7 Documentation Agent detects Laravel/Sanctum and fetches docs
# 3. Codebase Pattern Analyst finds existing auth patterns
# 4. PRP Quality Validator ensures 8+ quality scores before saving
```

### Executing a PRP with Systematic Implementation
```bash
# Standard execution - implementation coordinator takes over
/execute-base-prp PRPs/user-auth-2025-01-01.md

# What happens automatically:
# 1. PRP Implementation Coordinator loads and analyzes the PRP
# 2. Creates systematic implementation plan with TodoWrite
# 3. Executes with proper validation loops at each level
# 4. Handles errors and iterations systematically
# 5. Generates comprehensive implementation report
```

### Manual Subagent Invocation
```bash
# Explicit subagent usage when needed
> Use the context7-documentation-agent to get current Astro docs for SSG
> Have the codebase-pattern-analyst find existing API patterns
> Ask the prp-quality-validator to validate this generated PRP
```

## Subagent File Locations

All subagents are stored **globally** in `~/.claude/agents/` for universal availability:

```
~/.claude/agents/
├── prp-research-specialist.md      # Comprehensive research coordination
├── prp-quality-validator.md        # Quality validation and scoring  
├── context7-documentation-agent.md # Technology detection and docs
├── prp-implementation-coordinator.md # Systematic implementation
└── codebase-pattern-analyst.md     # Pattern analysis and conventions
```

**Advantage**: These agents work across ALL your projects automatically, with easier maintenance and consistent quality.

## Integration with Context7

The subagent system fully integrates with Context7 for universal technology support:

- **Auto-detection**: ANY framework mentioned triggers Context7 integration
- **Universal support**: Frontend, backend, CMS, databases, tools
- **Current documentation**: Always fetches latest framework documentation
- **Topic-focused**: Documentation relevant to specific feature requirements

## Quality Standards

All subagents target these quality metrics:

### Research Quality (8+/10)
- Comprehensive Context7 documentation for all technologies
- Specific codebase pattern analysis with file references
- External research with actionable implementation guidance
- Project-specific configuration and validation patterns

### Implementation Quality (8+/10)
- Systematic execution following established patterns
- Proper validation loops at all levels
- Error handling with systematic resolution
- Comprehensive quality assurance and reporting

### Success Probability (8+/10)
- One-pass implementation success through comprehensive context
- Validated implementation approach with existing pattern alignment
- Quality gates ensuring robust, maintainable code
- Documentation and troubleshooting guidance included

## Next Steps

1. **Test the integration**: Try creating a PRP with `/prp-base-create` to see subagents in action
2. **Review generated PRPs**: Check quality scores and comprehensive context
3. **Execute a PRP**: Use `/execute-base-prp` to experience systematic implementation
4. **Customize as needed**: Modify subagent descriptions for project-specific needs

The subagent integration enhances your existing PRP methodology while maintaining the same user experience - everything just works better automatically.