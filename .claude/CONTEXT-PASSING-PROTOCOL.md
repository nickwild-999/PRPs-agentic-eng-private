# Context Passing Protocol for PRP Subagents

## Overview

This document defines the comprehensive context passing protocol to ensure ALL subagents receive complete information needed for successful task execution. Each subagent has been enhanced with explicit context validation requirements.

## Critical Context Validation

**RULE**: Before delegating to ANY subagent, you MUST validate and pass ALL required context. Subagents are instructed to STOP and request missing information if context is incomplete.

## Context Requirements by Subagent

### 1. PRP Research Specialist

**Required Context Input**:
```yaml
Feature Request Context:
  - complete_feature_description: "$ARGUMENTS with full user requirements"
  - technology_stack_mentioned: "Specific frameworks, libraries, tools"
  - business_context: "Why needed, how it fits project"
  - success_criteria: "What defines successful implementation"
  - constraints: "Limitations, performance requirements, restrictions"

Project Context:
  - project_type: "Web app, API, library, mobile app, etc."
  - current_architecture: "MVC, microservices, monolith, etc."
  - technology_stack: "Languages, frameworks, databases in use"
  - development_environment: "Local setup, CI/CD, deployment"
  - team_conventions: "Code style, testing, documentation standards"

Existing Research:
  - previous_findings: "Any existing analysis or documentation"
  - known_patterns: "Existing implementations of similar features"
  - integration_points: "How feature connects to existing systems"
  - dependencies: "What this depends on or what depends on it"

Quality Requirements:
  - performance_targets: "Response times, throughput, scalability"
  - security_requirements: "Auth, authorization, data protection"
  - testing_standards: "Coverage requirements, frameworks used"
  - compliance_needs: "Regulatory, accessibility, industry standards"
```

**Context Passing Example**:
```
Task: Comprehensive Research for Feature: "$ARGUMENTS"

Complete Context Package:
- Feature Description: [Full user request with requirements]
- Project Type: [Current project type and architecture]
- Technology Stack: [Current frameworks and tools in use]
- Business Context: [Why this feature is needed]
- Success Criteria: [What defines success]
- Quality Requirements: [Performance, security, testing needs]
- Existing Research: [Any previous analysis]
- Integration Points: [How this connects to existing systems]

Research all aspects of this feature with the provided context.
```

### 2. PRP Implementation Coordinator

**Required Context Input**:
```yaml
Complete PRP Context:
  - full_prp_content: "Entire PRP file with all sections"
  - goal_and_requirements: "Clear understanding of what to build"
  - success_criteria: "Specific measurable outcomes"
  - context_section: "All documentation, patterns, references"
  - implementation_blueprint: "Step-by-step tasks and pseudocode"
  - validation_gates: "All executable commands and quality checks"

Current Codebase State:
  - project_structure: "Current directory layout and organization"
  - existing_implementations: "Similar features in codebase"
  - code_conventions: "Naming, style, architectural patterns"
  - testing_framework: "Current test setup and coverage"
  - dependencies: "Installed packages, libraries, versions"

Environment Context:
  - development_setup: "Local environment configuration"
  - build_tools: "Compilation, bundling, dev server setup"
  - database_state: "Current schema, migrations, data"
  - configuration: "Environment variables, config files"
  - git_state: "Current branch, uncommitted changes"

Integration Context:
  - api_contracts: "Existing endpoints and data formats"
  - database_schema: "Tables, relationships, constraints"
  - external_services: "Third-party integrations and configs"
  - performance_requirements: "Response time, throughput, scalability"
  - security_considerations: "Auth, authorization, data protection"
```

**Context Passing Example**:
```
Task: Execute PRP Implementation: [PRP_FILENAME]

Complete Context Package:
- PRP Content: [Full PRP file content]
- Project Structure: [Current directory layout]
- Environment Status: [Dependencies, build tools, database]
- Git State: [Current branch, uncommitted changes]
- Integration Points: [API contracts, database schema]
- Code Conventions: [Existing patterns to follow]
- Validation Commands: [All executable validation gates]

Implement the PRP systematically with provided context.
```

### 3. Context7 Documentation Agent

**Required Context Input**:
```yaml
Technology Detection Context:
  - feature_description: "Complete user request for technology detection"
  - mentioned_technologies: "Explicit frameworks/libraries mentioned"
  - implied_technologies: "Technologies implied by feature type"
  - current_stack: "Technologies already in use in project"

Documentation Focus:
  - specific_topics: "Relevant topics for the feature (auth, API, etc.)"
  - integration_needs: "How technologies work together"
  - version_requirements: "Specific versions if important"
  - implementation_context: "How docs will be used in PRP"
```

### 4. PRP Quality Validator

**Required Context Input**:
```yaml
PRP Validation Context:
  - complete_prp_content: "Full PRP content to validate"
  - quality_targets: "Target scores for each dimension (8+/10)"
  - project_context: "Project type and complexity"
  - implementation_context: "How PRP will be used"

Validation Criteria:
  - context_richness_requirements: "What constitutes sufficient context"
  - implementation_clarity_standards: "What makes clear implementation"
  - validation_completeness_needs: "Required validation levels"
  - success_probability_factors: "What increases implementation success"
```

### 5. Codebase Pattern Analyst

**Required Context Input**:
```yaml
Analysis Context:
  - feature_description: "What to analyze patterns for"
  - current_codebase_scope: "Directories and files to analyze"
  - similar_features: "What to look for as similar implementations"
  - pattern_types_needed: "Architectural, testing, integration patterns"

Project Context:
  - technology_stack: "Languages, frameworks, tools in use"
  - architecture_type: "MVC, microservices, etc."
  - code_organization: "How code is structured"
  - testing_approach: "Testing frameworks and patterns"
```

## Context Passing Protocol by Command

### For `/prp-base-create $ARGUMENTS`

**Step 1: Gather Complete Context**
```bash
# Before delegating to subagents, collect:
1. Read CLAUDE.md for project conventions
2. Analyze current project structure (ls, tree)
3. Check technology stack (package.json, composer.json, etc.)
4. Review existing similar features
5. Understand development environment
```

**Step 2: Delegate with Full Context**
```
Task: Use prp-research-specialist for comprehensive research

Complete Context:
- Feature Request: "$ARGUMENTS" 
- Project Type: [Determined from analysis]
- Current Tech Stack: [Languages, frameworks, databases]
- Architecture: [MVC, microservices, etc.]
- Business Context: [Why this feature is needed]
- Quality Requirements: [Performance, security, testing standards]
- Development Environment: [Setup, tools, configurations]
- Existing Patterns: [Similar implementations found]

Research this feature comprehensively with all provided context.
```

### For `/execute-base-prp $ARGUMENTS`

**Step 1: Load Complete PRP and Environment Context**
```bash
# Before delegating to implementation coordinator:
1. Read complete PRP file: $ARGUMENTS
2. Analyze current codebase state
3. Check git status and environment
4. Verify dependencies and build tools
5. Understand integration requirements
```

**Step 2: Delegate with Full Context**
```
Task: Use prp-implementation-coordinator for systematic execution

Complete Context:
- PRP Content: [Full PRP file content]
- Current Project State: [Directory structure, git status]
- Environment Status: [Dependencies, build tools, database]
- Integration Context: [API contracts, database schema]
- Code Conventions: [Patterns to follow from PRP research]
- Validation Requirements: [All validation gates from PRP]

Execute this PRP systematically with all provided context.
```

## Context Validation Checklist

**Before ANY subagent delegation**:

### Research Phase (PRP Research Specialist)
- [ ] Complete feature description understood
- [ ] Project technology stack identified  
- [ ] Current architecture and patterns analyzed
- [ ] Business context and success criteria defined
- [ ] Quality and performance requirements known
- [ ] Development environment understood
- [ ] Existing research and patterns documented

### Implementation Phase (PRP Implementation Coordinator)  
- [ ] Complete PRP content read and understood
- [ ] Current codebase state analyzed
- [ ] Development environment verified functional
- [ ] All dependencies and tools available
- [ ] Integration points identified and understood
- [ ] Validation commands tested and confirmed executable
- [ ] Code conventions and patterns identified

### Quality Validation (PRP Quality Validator)
- [ ] Complete PRP content available for validation
- [ ] Quality targets and standards defined
- [ ] Project context understood for appropriate validation
- [ ] Success criteria clear for probability assessment

## Error Handling for Missing Context

**If subagent reports missing context**:
1. **Stop current workflow**
2. **Gather missing information** using appropriate tools
3. **Re-delegate with complete context**
4. **Document context requirements** for future use

**Common Missing Context Patterns**:
- Feature requirements unclear or incomplete
- Project technology stack not analyzed
- Current codebase patterns not researched
- Development environment not verified
- Integration points not identified
- Validation requirements not defined

## Success Criteria

Context passing is successful when:
- Subagents receive ALL required information without asking for clarification
- No "missing context" errors from subagents
- Subagents produce high-quality outputs with complete context
- Implementation success rate improves due to comprehensive context
- Reduced iterations needed due to proper upfront context gathering

## Best Practices

1. **Front-load context gathering**: Spend time upfront collecting comprehensive context
2. **Use structured context packages**: Organize context systematically for subagents
3. **Validate context completeness**: Check all requirements before delegation
4. **Document context patterns**: Record successful context patterns for reuse
5. **Iterate context protocols**: Improve based on subagent feedback and success rates

Remember: Comprehensive context is the foundation of one-pass implementation success. Subagents can only be as good as the context they receive.