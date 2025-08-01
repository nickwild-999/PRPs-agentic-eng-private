# PRPs Agentic Engineering Framework

A comprehensive framework for AI-assisted development with **automated PRP creation**, **multi-stack support**, and **production-ready workflows**. Delivers one-pass implementation success through context engineering and structured validation.

> **📍 Original Repository:** https://github.com/Wirasm/PRPs-agentic-eng  
> **🎥 Video Walkthrough:** https://www.youtube.com/watch?v=KVOZ9s1S9Gk  
> **👨‍💻 Created by:** [Rasmus Widing](https://www.rasmuswiding.com/) (@wirasm)
> 
> This enhanced fork includes auto-save functionality, Laravel 12 support, and multi-stack improvements.

## 🎯 What is PRP?

**Product Requirement Prompt (PRP) = PRD + curated codebase intelligence + agent/runbook**

A PRP supplies an AI coding agent with everything it needs to deliver a vertical slice of working software—no more, no less. Unlike traditional PRDs, PRPs include executable context, validation gates, and implementation blueprints for AI agents.

## 🚀 Recent Enhancements

### ✨ **Auto-Save PRP Creation with Context7 Integration**
- All PRP creation commands now automatically save to `PRPs/` directory
- **Context7 Documentation**: Automatically pulls current framework docs during PRP creation
- **Smart Technology Detection**: Auto-detects Laravel, React, Next.js, etc. from requests
- **Live Documentation**: Includes up-to-date library docs directly in PRPs
- Timestamped filenames (e.g., `user-auth-2025-01-01.md`)
- No more manual copy/paste - fully automated workflow

### 🛠️ **Multi-Stack Support**
- **Laravel 12** with Livewire 3 + Filament 3 (comprehensive guide included)
- **React/Next.js** with TypeScript
- **Node.js** applications
- **Python** projects (optional)

### 📋 **28+ Claude Commands**
- Organized command structure for different development phases
- **Context7 Documentation Integration**: Auto-pulls current framework docs
- Parallel research agents for comprehensive context gathering
- Technology-specific validation patterns

### 🔄 **Context7 Auto-Documentation**
- **Smart Detection**: Automatically identifies ANY frameworks from requests (Astro, React, Laravel, Sanity, etc.)
- **Live Documentation**: Fetches current, up-to-date library documentation during PRP creation
- **Comprehensive Context**: Includes API references, best practices, and implementation patterns
- **Universal Coverage**: Works with ANY technology stack - Astro, React, Laravel, Sanity, Python, Node.js, and more
- **Automatic Integration**: No manual documentation lookup required

---

## 📺 Video Walkthrough

👉 https://www.youtube.com/watch?v=KVOZ9s1S9Gk&lc=UgzfwxvFjo6pKEyPo1R4AaABAg

## ☕ Support This Work

**Found value in these resources?**

👉 **Buy me a coffee:** https://coff.ee/wirasm

I spent considerable time creating these resources and prompts. If you find value in this project, please consider buying me a coffee to support my work and help me maintain and improve these resources.

---

## 🎯 Transform Your Team with AI Engineering Workshops

**Ready to move beyond toy demos to production-ready AI systems?**

👉 **Book a workshop:** https://www.rasmuswiding.com/

✅ **What you'll get:**
- Put your team on a path to become AI power users
- Learn the exact PRP methodology used by top engineering teams
- Hands-on training with Claude Code, PRPs, and real codebases
- From beginner to advanced AI engineering workshops for teams and individuals

💡 **Perfect for:** Engineering teams, Product teams, and developers who want AI that actually works in production

**Contact:** rasmus@widinglabs.com

---

## 🏗️ Framework Architecture

### **Command-Driven System**
- **28+ pre-configured Claude Code commands** in `.claude/commands/`
- Commands organized by function:
  - `PRPs/` - PRP creation and execution workflows  
  - `development/` - Core utilities (prime-core, onboarding, debug)
  - `code-quality/` - Review and refactoring commands
  - `rapid-development/experimental/` - Parallel PRP creation tools
  - `git-operations/` - Smart git operations and conflict resolution

### **Auto-Save PRP Templates**
- **PRP Templates** in `PRPs/templates/` with structured validation loops
- **Automated saving** - no manual file management required
- **Context-Rich Approach** - comprehensive documentation and examples included
- **Validation-First Design** - executable validation gates for each technology stack

### **Multi-Stack CLAUDE.md Files**
- `claude_md_files/CLAUDE-LARAVEL-12.md` - Laravel 12 with Livewire 3 + Filament 3
- `claude_md_files/CLAUDE-REACT.md` - React applications
- `claude_md_files/CLAUDE-NEXTJS-15.md` - Next.js 15 applications  
- `claude_md_files/CLAUDE-PYTHON-BASIC.md` - Python projects

---

## 🚀 Quick Start

### Option 1: Use Original Repository (Recommended)

For the latest official version:

```bash
# Clone the original repository
git clone https://github.com/Wirasm/PRPs-agentic-eng.git
cd PRPs-agentic-eng
```

### Option 2: Use Enhanced Private Fork (With Auto-Save Features)

If you want the enhanced version with auto-save functionality and Laravel 12 support:

```bash
# Clone the enhanced private fork
git clone https://github.com/nickwild-999/PRPs-agentic-eng-private.git
cd PRPs-agentic-eng-private

# Keep updated with original repository
git remote add upstream https://github.com/Wirasm/PRPs-agentic-eng.git
git fetch upstream
git merge upstream/development
```

### Option 3: Copy Framework to Existing Project

```bash
# Copy framework to your project
cp -r /path/to/PRPs-agentic-eng/.claude .
cp -r /path/to/PRPs-agentic-eng/PRPs .

# Copy appropriate CLAUDE.md for your stack
cp /path/to/PRPs-agentic-eng/claude_md_files/CLAUDE-LARAVEL-12.md ./CLAUDE.md
# or
cp /path/to/PRPs-agentic-eng/claude_md_files/CLAUDE-REACT.md ./CLAUDE.md
```

### Option 4: Framework-Specific Complete Setup

For complete setup with any framework:

```bash
# Follow the comprehensive setup guide for any stack
cat PROJECT-SETUP-GUIDE.md

# Quick start examples:

# Laravel project:
mkdir my-laravel-project && cd my-laravel-project
cp -r /path/to/PRPs-agentic-eng/.claude .
cp -r /path/to/PRPs-agentic-eng/PRPs .
cp /path/to/PRPs-agentic-eng/claude_md_files/CLAUDE-LARAVEL-12.md ./CLAUDE.md
composer create-project laravel/laravel . "^12.0"

# Astro project:
mkdir my-astro-project && cd my-astro-project
cp -r /path/to/PRPs-agentic-eng/.claude .
cp -r /path/to/PRPs-agentic-eng/PRPs .
cp /path/to/PRPs-agentic-eng/claude_md_files/CLAUDE-REACT.md ./CLAUDE.md
npm create astro@latest . -- --template minimal --typescript

# See PROJECT-SETUP-GUIDE.md for complete instructions for any framework
```

---

## 💻 Development Workflow

### **1. Project Planning**
```bash
# Create comprehensive project planning PRP with Context7 docs (auto-saves)
/prp-planning-create blog platform with Astro and Sanity CMS

# ✅ Auto-detects: Astro, Sanity CMS frameworks
# ✅ Auto-fetches: Current Astro, Sanity documentation and best practices
# ✅ Auto-saved to: PRPs/blog-platform-planning-2025-08-01.md

# Or for Laravel projects:
/prp-planning-create compliance system with Laravel and React
# ✅ Auto-detects: Laravel, React frameworks
# ✅ Auto-fetches: Current Laravel, React documentation
```

### **2. Implementation PRP Creation**
```bash
# Create focused implementation PRPs with Context7 docs (auto-saves)
/prp-base-create user authentication with Laravel built-in auth
/prp-base-create React component library with TypeScript
/prp-base-create Astro blog with Sanity content management

# ✅ Auto-detects: Laravel/React/Astro, TypeScript, Sanity
# ✅ Auto-fetches: Current documentation for detected technologies
# ✅ Auto-saved to: PRPs/user-auth-2025-08-01.md (with Context7 docs)
# ✅ Auto-saved to: PRPs/react-components-2025-08-01.md (with Context7 docs)
# ✅ Auto-saved to: PRPs/astro-blog-2025-08-01.md (with Context7 docs)
```

### **3. Code Implementation**
```bash
# Execute PRPs in dependency order
/execute-base-prp PRPs/user-auth-2025-01-01.md
/execute-base-prp PRPs/multi-step-forms-2025-01-01.md
/execute-base-prp PRPs/filament-admin-2025-01-01.md
```

### **4. Validation & Quality**
```bash
# Technology-specific validation (automatically included in PRPs)
# Laravel:
vendor/bin/pint && vendor/bin/phpstan analyse && php artisan test

# Node.js/React:
npm run lint && npm run type-check && npm run test

# Python:
ruff check --fix && mypy . && pytest tests/ -v
```

---

## 🛠️ Available Claude Commands

### **PRP Creation (Auto-Save + Context7 Enabled)**
- `/prp-base-create` - Generate comprehensive PRPs with Context7 docs, research and auto-save
- `/prp-planning-create` - Create project planning PRPs with Context7 architectural guidance and auto-save  
- `/prp-spec-create` - Generate specification PRPs with Context7 migration docs and auto-save
- `/prp-task-create` - Create focused task PRPs with Context7 task-specific docs and auto-save
- `/TS-create-base-prp` - TypeScript-specific PRP creation
- `/create-base-prp-parallel` - Parallel research PRP creation with Context7 integration
- `/create-planning-parallel` - Parallel planning PRP creation with Context7 docs

### **PRP Execution**
- `/execute-base-prp` - Execute saved PRPs against codebase
- `/prp-validate` - Validate PRP completeness  
- `/prp-analyze-run` - Analyze and execute PRPs

### **Code Quality & Review**
- `/review-general` - General code review
- `/review-staged-unstaged` - Review git stage/unstaged changes
- `/refactor-simple` - Simple refactoring tasks

### **Development Utilities**
- `/prime-core` - Prime Claude with comprehensive project context
- `/onboarding` - Onboarding workflow for new team members
- `/debug` - Advanced debugging workflow
- `/create-pr` - Create GitHub pull requests

### **Git Operations**
- Advanced git conflict resolution
- Intelligent merge strategies
- Smart branch management

---

## 📁 Project Structure

```
PRPs-agentic-eng/
├── .claude/
│   ├── commands/              # 28+ Claude Code commands
│   │   ├── PRPs/             # PRP creation and execution
│   │   ├── development/      # Core development utilities
│   │   ├── code-quality/     # Review and refactoring
│   │   ├── rapid-development/# Parallel creation tools
│   │   └── git-operations/   # Git workflow commands
│   └── settings.local.json   # Tool permissions
├── PRPs/
│   ├── templates/            # Auto-save PRP templates
│   ├── scripts/             # Python runner (optional)
│   ├── ai_docs/             # Curated Claude Code documentation
│   └── *.md                 # Generated PRPs (auto-saved here)
├── claude_md_files/          # Framework-specific CLAUDE.md files
│   ├── CLAUDE-LARAVEL-12.md # Laravel 12 + Livewire 3 + Filament 3
│   ├── CLAUDE-REACT.md      # React applications
│   ├── CLAUDE-NEXTJS-15.md  # Next.js 15 applications
│   └── CLAUDE-PYTHON-BASIC.md # Python projects
├── LARAVEL-SETUP-GUIDE.md   # Complete Laravel 12 setup guide
└── pyproject.toml           # Framework configuration (optional)
```

---

## 🔧 Technology Support

### **Laravel 12** (Full Support)
- **Livewire 3** integration with reactive components
- **Filament 3** admin panel with resources and dashboards
- **PHP 8.3+** with strict typing
- **Comprehensive validation** with Form Requests and Policies
- **Complete setup guide** in `LARAVEL-SETUP-GUIDE.md`

### **React/Next.js** (Full Support)
- **Next.js 15** with App Router and Server Components
- **React 19** with modern patterns
- **TypeScript** strict configuration
- **Testing** with Vitest and React Testing Library

### **Node.js** (Full Support)
- **Modern JavaScript/TypeScript** patterns
- **Package management** with npm/yarn/pnpm
- **Testing frameworks** integration

### **Python** (Optional Support)
- **Python 3.12+** with UV package management
- **FastAPI/Django** patterns
- **Pytest** testing framework
- **PRP runner** for command-line execution

---

## 🎯 PRP Methodology

### **What Makes a Great PRP**

1. **Context-Rich Documentation**
   - Specific URLs with relevant sections
   - Real code examples from codebase
   - Library quirks and gotchas
   - Existing patterns to follow

2. **Implementation Blueprint**
   - Pseudocode showing approach
   - Task breakdown with dependencies
   - Error handling strategies
   - Integration points

3. **Executable Validation Gates**
   ```bash
   # Level 1: Syntax & Style
   vendor/bin/pint && vendor/bin/phpstan analyse
   
   # Level 2: Unit Tests  
   php artisan test --coverage
   
   # Level 3: Integration Tests
   curl -X POST http://localhost:8000/api/endpoint
   
   # Level 4: Creative Validation
   # MCP servers, load testing, etc.
   ```

4. **Auto-Save Integration**
   - All PRPs automatically saved with timestamps
   - No manual file management required
   - Clear success messages with file paths

---

## 🔄 Keep Your Fork Updated

If using the private fork, stay updated with the original repository:

```bash
# Add upstream remote (one time setup)
git remote add upstream https://github.com/Wirasm/PRPs-agentic-eng.git

# Update your fork
git fetch upstream
git checkout development  
git merge upstream/development

# Push updates to your private fork
git push origin development
```

---

## 🎯 Best Practices

### **PRP Creation**
1. **Use planning PRPs first** for complex projects
2. **Break large features** into focused implementation PRPs  
3. **Include comprehensive context** - documentation, examples, gotchas
4. **Define clear validation gates** that AI can execute
5. **Review auto-saved PRPs** before execution

### **Technology Selection**
1. **Copy appropriate CLAUDE.md** for your tech stack
2. **Customize validation commands** for your specific setup
3. **Follow framework conventions** (Laravel, React, etc.)
4. **Use recommended packages** from the CLAUDE.md guides

### **Workflow Management**
1. **Execute PRPs in dependency order**
2. **Validate after each implementation**
3. **Commit working code** before moving to next PRP
4. **Use version control** throughout the process

---

## 📚 Additional Resources

- **Project Setup Guide**: `PROJECT-SETUP-GUIDE.md` - Complete step-by-step setup for ANY framework
- **Context7 Integration Guide**: `CONTEXT7-INTEGRATION-GUIDE.md` - Complete Context7 documentation integration
- **AI Documentation**: `PRPs/ai_docs/` - Curated Claude Code documentation
- **Example PRPs**: `PRPs/example-*.md` - Real-world PRP examples
- **Video Walkthrough**: https://www.youtube.com/watch?v=KVOZ9s1S9Gk

---

## 🙏 Acknowledgments

This enhanced fork builds upon the excellent work of **[Rasmus Widing](https://www.rasmuswiding.com/)** (@wirasm) and the original **PRPs Agentic Engineering Framework**.

### **Original Framework:**
- **Repository**: https://github.com/Wirasm/PRPs-agentic-eng
- **Creator**: Rasmus Widing - AI Engineering consultant and workshop leader
- **Methodology**: Context Engineering principles and PRP development
- **Community**: Active workshops and training programs

### **Enhancements in This Fork:**
- Auto-save PRP creation functionality
- Laravel 12 with Livewire 3 + Filament 3 support
- Multi-stack validation patterns
- Comprehensive setup guides
- Technology-specific CLAUDE.md files

## 🤝 Contributing

### **To Original Repository:**
Please contribute to the main project at: https://github.com/Wirasm/PRPs-agentic-eng

### **To This Enhanced Fork:**
Contributions to enhancements welcome:

1. Fork this repository
2. Create feature branch
3. Add comprehensive tests
4. Update documentation
5. Submit pull request

**Note**: Major framework improvements should be submitted to the original repository first.

---

## 📄 License

MIT License - see LICENSE file for details.

---

**Remember: The goal is one-pass implementation success through comprehensive context and automated workflows. Every PRP should contain the exact context for an AI agent to successfully implement working code in a single pass.**

---

*Last updated: January 2025 - Enhanced with Laravel 12 support, auto-save functionality, and multi-stack architecture.*