# Context7 Integration Guide

## Overview

The PRPs framework now includes **automatic Context7 documentation integration** to enhance PRP creation with current, comprehensive framework documentation. This eliminates the need for manual documentation lookup and ensures PRPs always include the latest technical information.

## How It Works

### Automatic Technology Detection

When you create a PRP, the system automatically detects relevant technologies from your request:

```bash
# Example: This request automatically detects Laravel, Sanctum, and Livewire
/prp-base-create user authentication system with Laravel Sanctum and Livewire components

# System detects: Laravel, Sanctum, Livewire
# Auto-fetches: Current docs for each technology
# Includes: API references, best practices, implementation patterns
```

### Supported Technologies

Context7 integration works with ANY frameworks and libraries:

- **Frontend**: Astro, React, Vue.js, Next.js, Svelte, Angular
- **Backend**: Laravel, Node.js, Python (Django/FastAPI), Ruby on Rails
- **CMS**: Sanity, Strapi, Contentful, WordPress
- **Databases**: PostgreSQL, MongoDB, Redis, SQLite
- **Languages**: TypeScript, JavaScript, PHP, Python, Go
- **Tools**: Vite, Webpack, Docker, Tailwind CSS
- **And hundreds more...**

## Enhanced PRP Commands

All PRP creation commands now include Context7 integration:

### `/prp-base-create` - Base Implementation PRPs
```bash
# Example 1: Astro + Sanity stack
/prp-base-create blog system with Astro and Sanity CMS
# 1. Detects: Astro, Sanity
# 2. Fetches: Astro SSG docs, Sanity integration guides
# 3. Includes: Performance patterns, content modeling
# 4. Saves: Comprehensive PRP with live documentation

# Example 2: Laravel with built-in auth (not Sanctum)
/prp-base-create user authentication with Laravel built-in auth
# 1. Detects: Laravel
# 2. Fetches: Laravel authentication docs (built-in, not Sanctum)
# 3. Includes: Session-based auth, middleware patterns
# 4. Saves: Authentication PRP with standard Laravel auth
```

### `/prp-planning-create` - Project Planning PRPs
```bash
# Example 1: Modern stack
/prp-planning-create portfolio website with Astro and TypeScript
# 1. Detects: Astro, TypeScript
# 2. Fetches: Astro architecture docs, TypeScript patterns
# 3. Includes: Performance optimization, type safety
# 4. Saves: Planning document with modern web architecture

# Example 2: Full-stack
/prp-planning-create SaaS application with React and Laravel API
# 1. Detects: React, Laravel
# 2. Fetches: React SPA patterns, Laravel API documentation
# 3. Includes: Authentication flows, state management
# 4. Saves: Full-stack planning document
```

### `/prp-spec-create` - Specification PRPs
```bash
/prp-spec-create migrate Laravel 11 to Laravel 12 with Livewire upgrade

# What happens:
# 1. Detects: Laravel, Livewire, migration scenario
# 2. Fetches: Migration guides, breaking changes, upgrade paths
# 3. Includes: Version-specific differences, compatibility notes
# 4. Saves: Detailed migration specification
```

### `/prp-task-create` - Focused Task PRPs
```bash
/prp-task-create add Redis caching to Laravel application

# What happens:
# 1. Detects: Laravel, Redis
# 2. Fetches: Caching documentation, Redis integration guides
# 3. Includes: Configuration examples, performance optimization
# 4. Saves: Task-focused implementation guide
```

## Enhanced PRP Content

### Before Context7 Integration
```markdown
## All Needed Context
- url: https://laravel.com/docs/authentication (manual lookup required)
- file: app/Models/User.php
- note: Check Laravel docs for latest Sanctum setup
```

### After Context7 Integration
```markdown
## All Needed Context

### Context7 Documentation (Auto-fetched)
**Laravel Framework:**
- Authentication: Current Laravel authentication patterns and best practices
- API Security: Sanctum token management and security considerations
- Database: Eloquent relationships and query optimization
- Testing: PHPUnit integration and testing strategies

**Sanctum Package:**
- Token Authentication: SPA and API token authentication setup
- Configuration: Environment variables and security settings
- Middleware: Route protection and token validation

### Additional Documentation
- url: https://laravel.com/docs/authentication (supplementary reference)
- file: app/Models/User.php (existing implementation)
```

## Benefits

### 1. **Always Current Documentation**
- Fetches the latest version of framework documentation
- Includes recent API changes and best practices
- Eliminates outdated information in PRPs

### 2. **Comprehensive Context**
- Automatically includes relevant sections
- Covers security considerations and gotchas
- Provides implementation examples and patterns

### 3. **Reduced Manual Work**
- No need to manually lookup documentation
- Automatic technology detection
- Seamless integration into existing workflow

### 4. **Higher Success Rate**
- More complete context leads to better implementations
- Current best practices reduce debugging
- Framework-specific patterns improve code quality

## Advanced Usage

### Manual Context7 Usage
You can also manually fetch documentation when needed:

```bash
# In Claude Code, resolve library first
/resolve-library-id laravel

# Then fetch specific documentation
/get-library-docs /laravel/laravel authentication security

# Use the documentation in your PRP creation
/prp-base-create authentication system using the Context7 docs above
```

### Multiple Framework Detection
The system handles multiple frameworks intelligently:

```bash
/prp-base-create full-stack application with React frontend and Laravel API

# Detects: React, Laravel
# Fetches: React component patterns, Laravel API documentation
# Includes: Integration patterns between frontend and backend
```

### Topic-Specific Documentation
Context7 can focus on specific topics:

```bash
/prp-base-create Laravel application with focus on testing

# Fetches: Laravel testing documentation specifically
# Includes: PHPUnit setup, feature testing, database testing
# Emphasizes: Testing best practices and patterns
```

## Configuration

### Framework Detection Patterns
The system recognizes frameworks through various patterns:

- **Explicit mentions**: "Laravel Sanctum", "React hooks", "Next.js App Router"
- **Context clues**: "authentication API", "component library", "server-side rendering"
- **Technology combinations**: "full-stack", "SPA", "REST API"

### Documentation Focus Areas
Context7 automatically selects relevant documentation sections:

- **Authentication requests**: Security, authentication, authorization docs
- **Database requests**: ORM, migrations, relationships documentation
- **API requests**: REST patterns, validation, response formatting
- **Frontend requests**: Component patterns, state management, routing

## Best Practices

### 1. **Be Specific in Requests**
```bash
# Good: Specific technology and use case
/prp-base-create Laravel Livewire form with file upload validation

# Better: Even more specific requirements
/prp-base-create Laravel Livewire multi-step form with image upload, validation, and progress tracking
```

### 2. **Review Context7 Documentation**
Always review the auto-fetched documentation in your PRPs:
- Verify it matches your use case
- Note any framework-specific considerations
- Check for security recommendations

### 3. **Combine with Codebase Analysis**
Context7 docs work best combined with codebase patterns:
- Use existing project conventions
- Follow established architectural patterns
- Maintain consistency with current implementation

### 4. **Update Documentation References**
When frameworks release updates:
- Re-run PRP creation for updated docs
- Review breaking changes in Context7 content
- Update existing PRPs if needed

## Troubleshooting

### Context7 Integration Issues

**Problem**: Framework not detected automatically
```bash
# Solution: Be more explicit in your request
/prp-base-create user authentication using Laravel 12 with Sanctum package
```

**Problem**: Wrong documentation fetched
```bash
# Solution: Specify the exact library or version
/prp-base-create React application using React 19 with hooks
```

**Problem**: Missing Context7 integration
```bash
# Check: Ensure MCP Context7 server is available
# Verify: Context7 tools are accessible in Claude Code
# Fallback: Use manual documentation lookup
```

### Documentation Quality

**Best Results**: Combine Context7 with existing patterns
- Use Context7 for current best practices
- Reference existing codebase for project-specific patterns
- Include both in PRP context section

**Version Compatibility**: Ensure framework versions match
- Specify versions in requests when important
- Cross-reference with project dependencies
- Note any version-specific considerations

## Examples

### Astro + Sanity Example
```bash
/prp-base-create blog platform with Astro and Sanity CMS

# Auto-detects: Astro, Sanity
# Fetches: Astro SSG docs, Sanity schema design, content delivery
# Result: Complete blog system PRP with static generation and headless CMS
```

### React Component Library Example
```bash
/prp-base-create design system with React and TypeScript

# Auto-detects: React, TypeScript
# Fetches: React component patterns, TypeScript integration, design system practices
# Result: Type-safe component library PRP with modern React patterns
```

### Laravel with Standard Auth Example
```bash
/prp-base-create user management with Laravel built-in authentication

# Auto-detects: Laravel (standard auth, not Sanctum)
# Fetches: Laravel authentication docs, session management, middleware
# Result: Traditional Laravel auth PRP with session-based authentication
```

### Mixed Stack Example
```bash
/prp-planning-create content site with Astro frontend and Sanity backend

# Auto-detects: Astro, Sanity, static generation patterns
# Fetches: Astro-Sanity integration, performance optimization, content modeling
# Result: Comprehensive JAMstack planning document with CMS integration
```

## Integration with Existing Workflow

The Context7 integration enhances your existing PRP workflow without changes:

1. **Create PRPs as usual** - Context7 works automatically
2. **Review generated PRPs** - Now includes comprehensive documentation
3. **Execute PRPs** - Better context leads to higher success rates
4. **Validate results** - Framework best practices reduce issues

Your existing commands work exactly the same, but now include live documentation automatically.

---

**Result**: Your PRPs now include comprehensive, current framework documentation automatically, leading to higher implementation success rates and better code quality.