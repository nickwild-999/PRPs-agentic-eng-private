# Project Setup Guide with PRPs Framework

Complete step-by-step guide to set up ANY new project using the PRPs-agentic-eng framework for AI-assisted development with Context7 documentation integration.

## Prerequisites

- **Git** - Version control
- **Claude Code CLI** - AI development assistant
- **Node.js 18+** - For most modern frameworks
- **Python 3.12+ with UV** (optional, for Python runner)
- **Framework-specific tools** (see framework sections below)

---

## Stage 1: Universal Project Foundation

### 1.1 Create Project Directory
```bash
# Create your project directory
mkdir my-awesome-project
cd my-awesome-project

# Initialize git
git init
```

### 1.2 Copy PRPs Framework
```bash
# Copy the entire PRPs framework to your project
cp -r /path/to/PRPs-agentic-eng/.claude .
cp -r /path/to/PRPs-agentic-eng/PRPs .

# Optional: Copy Python runner if you want to use it
cp -r /path/to/PRPs-agentic-eng/pyproject.toml .
```

### 1.3 Setup Framework-Specific CLAUDE.md

Choose the appropriate CLAUDE.md file for your technology stack:

#### For Laravel Projects
```bash
cp /path/to/PRPs-agentic-eng/claude_md_files/CLAUDE-LARAVEL-12.md ./CLAUDE.md
```

#### For React Projects
```bash
cp /path/to/PRPs-agentic-eng/claude_md_files/CLAUDE-REACT.md ./CLAUDE.md
```

#### For Next.js Projects
```bash
cp /path/to/PRPs-agentic-eng/claude_md_files/CLAUDE-NEXTJS-15.md ./CLAUDE.md
```

#### For Python Projects
```bash
cp /path/to/PRPs-agentic-eng/claude_md_files/CLAUDE-PYTHON-BASIC.md ./CLAUDE.md
```

#### For Custom Stack
```bash
# Start with the closest match and customize
cp /path/to/PRPs-agentic-eng/claude_md_files/CLAUDE-REACT.md ./CLAUDE.md
# Then edit CLAUDE.md to match your specific stack
```

**Note**: The file MUST be named exactly `CLAUDE.md` in your project root.

---

## Stage 2: Framework-Specific Setup

### Option A: Laravel Project Setup

#### Prerequisites
- PHP 8.3+
- Composer

#### Installation
```bash
# Create Laravel project
composer create-project laravel/laravel . "^12.0" --prefer-dist

# Install essential Laravel packages
composer require laravel/sanctum laravel/tinker

# Install Livewire and Filament (if needed)
composer require livewire/livewire filament/filament

# Install development tools
composer require --dev laravel/pint phpstan/phpstan pest/pest

# Setup environment
cp .env.example .env
php artisan key:generate
touch database/database.sqlite
php artisan migrate

# Install frontend assets
npm install
npm run build
```

### Option B: Astro Project Setup

#### Prerequisites
- Node.js 18+

#### Installation
```bash
# Create Astro project
npm create astro@latest . -- --template minimal --typescript

# Install dependencies
npm install

# Install additional packages (if needed)
npm install @sanity/client @astro/tailwind

# Setup environment
echo "# Environment variables" > .env
echo "PUBLIC_SANITY_PROJECT_ID=your-project-id" >> .env

# Build and test
npm run build
npm run dev
```

### Option C: React Project Setup

#### Prerequisites
- Node.js 18+

#### Installation
```bash
# Create React project with Vite
npm create vite@latest . -- --template react-ts

# Install dependencies
npm install

# Install additional packages
npm install @tanstack/react-query axios

# Install development tools
npm install --save-dev eslint prettier @types/node

# Setup environment
echo "# Environment variables" > .env
echo "VITE_API_URL=http://localhost:3000" >> .env

# Build and test
npm run build
npm run dev
```

### Option D: Full-Stack Setup (Astro + Laravel API)

#### Frontend (Astro)
```bash
mkdir frontend
cd frontend
npm create astro@latest . -- --template minimal --typescript
npm install
cd ..
```

#### Backend (Laravel API)
```bash
mkdir backend
cd backend
composer create-project laravel/laravel . "^12.0"
composer require laravel/sanctum
cd ..
```

### Option E: Python Project Setup

#### Prerequisites
- Python 3.12+
- UV package manager

#### Installation
```bash
# Initialize Python project
uv init
uv add fastapi uvicorn

# Or for Django
uv add django

# Install development tools
uv add --dev pytest black mypy

# Setup environment
echo "# Environment variables" > .env
echo "DEBUG=True" >> .env

# Create basic structure
mkdir src tests
```

---

## Stage 3: Project Planning Phase

### 3.1 Create Project Planning PRP

```bash
# Open Claude Code in your project directory
claude

# Create planning PRP with Context7 documentation (auto-detects your stack)
/prp-planning-create [your-project-description]

# Examples for different stacks:
/prp-planning-create blog platform with Astro and Sanity CMS
/prp-planning-create e-commerce site with React and Laravel API
/prp-planning-create portfolio website with TypeScript and animations
/prp-planning-create data dashboard with Python FastAPI and React
```

**What happens:**
- ✅ **Auto-detects technologies** from your description
- ✅ **Fetches Context7 docs** for detected frameworks
- ✅ **Generates comprehensive planning** document
- ✅ **Auto-saves** to `PRPs/{project-name}-planning-{YYYY-MM-DD}.md`
- ✅ **Includes architecture**, user stories, technical implementation

### 3.2 Review Planning PRP
```bash
# Review the generated planning PRP
cat PRPs/*-planning-*.md

# Edit if needed
nano PRPs/*-planning-*.md
```

---

## Stage 4: Implementation PRP Creation

Based on your planning PRP, create focused implementation PRPs:

### 4.1 Authentication System
```bash
# Laravel built-in auth
/prp-base-create user authentication with Laravel built-in auth

# Laravel with Sanctum (API)
/prp-base-create API authentication with Laravel Sanctum

# React authentication
/prp-base-create React authentication with JWT tokens

# Astro authentication
/prp-base-create Astro authentication with session management
```

### 4.2 Content Management
```bash
# Sanity CMS integration
/prp-base-create content management with Sanity CMS and Astro

# Laravel admin panel
/prp-base-create admin panel with Laravel and Filament

# React content editor
/prp-base-create content editor with React and rich text
```

### 4.3 Frontend Components
```bash
# React component library
/prp-base-create design system with React and TypeScript

# Astro components
/prp-base-create reusable components with Astro and TypeScript

# Laravel Livewire components
/prp-base-create interactive forms with Laravel Livewire
```

### 4.4 API Development
```bash
# Laravel API
/prp-base-create REST API with Laravel and API resources

# FastAPI backend
/prp-base-create Python API with FastAPI and Pydantic

# Node.js API
/prp-base-create Node.js API with Express and TypeScript
```

---

## Stage 5: Code Implementation

### 5.1 Execute PRPs in Dependency Order

```bash
# Execute PRPs in logical order
/execute-base-prp PRPs/user-auth-[date].md
/execute-base-prp PRPs/content-management-[date].md
/execute-base-prp PRPs/frontend-components-[date].md
/execute-base-prp PRPs/api-development-[date].md
```

### 5.2 Validation After Each PRP

#### Laravel Projects
```bash
vendor/bin/pint                # Code formatting
vendor/bin/phpstan analyse     # Static analysis
php artisan test --coverage    # Tests
```

#### Astro/React Projects
```bash
npm run lint                   # ESLint
npm run type-check            # TypeScript
npm run test                  # Tests
npm run build                 # Build verification
```

#### Python Projects
```bash
uv run ruff check --fix       # Code formatting
uv run mypy .                 # Type checking
uv run pytest tests/ -v      # Tests
```

---

## Stage 6: Development Environment

### 6.1 Start Development Servers

#### Laravel
```bash
php artisan serve              # Laravel app (http://localhost:8000)
php artisan queue:work         # Queue processing
npm run dev                    # Vite asset building
```

#### Astro
```bash
npm run dev                    # Astro dev server (http://localhost:4321)
```

#### React
```bash
npm run dev                    # Vite dev server (http://localhost:5173)
```

#### Python FastAPI
```bash
uv run uvicorn main:app --reload  # FastAPI server (http://localhost:8000)
```

### 6.2 Test Application Features

#### API Testing
```bash
# Test API endpoints
curl -X POST http://localhost:8000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":"test@example.com","password":"password"}'
```

#### Frontend Testing
```bash
# Access your application
open http://localhost:4321  # Astro
open http://localhost:5173  # React
open http://localhost:8000  # Laravel
```

---

## Stage 7: Production Preparation

### 7.1 Environment Configuration

#### Universal Steps
```bash
# Create production environment file
cp .env.example .env.production

# Configure production settings:
# - Database connections
# - API keys and secrets
# - CDN and storage settings
# - Mail configuration
```

#### Framework-Specific Production Build

##### Laravel
```bash
php artisan config:cache
php artisan route:cache
php artisan view:cache
composer install --optimize-autoloader --no-dev
```

##### Astro/React
```bash
npm run build
npm run preview  # Test production build
```

##### Python
```bash
uv sync --no-dev
uv run python -m pytest  # Final test run
```

---

## Quick Reference Commands

### PRP Management (Works with ANY stack)
```bash
# Create planning PRP (auto-detects your stack)
/prp-planning-create [project-description]

# Create implementation PRP (auto-detects frameworks)
/prp-base-create [feature-description]

# Execute PRP
/execute-base-prp PRPs/[prp-file].md

# List PRPs
ls -la PRPs/*.md
```

### Framework-Agnostic Validation
```bash
# The Context7 integration provides appropriate commands for your stack:

# Laravel
vendor/bin/pint && vendor/bin/phpstan analyse && php artisan test

# Astro/React/Node.js
npm run lint && npm run type-check && npm run test && npm run build

# Python
uv run ruff check --fix && uv run mypy . && uv run pytest tests/ -v
```

---

## File Structure After Setup

```
my-awesome-project/
├── .claude/                    # Claude Code commands (universal)
│   ├── commands/              # 28+ Claude commands with Context7
│   └── settings.local.json    # Tool permissions
├── PRPs/                      # PRP files (universal)
│   ├── templates/            # PRP creation templates
│   ├── scripts/             # Python runner (optional)
│   ├── ai_docs/             # AI documentation
│   ├── *-planning-*.md      # Generated planning PRPs
│   └── *-*.md               # Generated implementation PRPs
├── CLAUDE.md                  # Framework-specific guidance
├── [FRAMEWORK FILES]          # Your chosen framework structure
│   ├── Laravel: app/, database/, routes/, etc.
│   ├── Astro: src/, public/, astro.config.mjs
│   ├── React: src/, public/, vite.config.ts
│   └── Python: src/, tests/, pyproject.toml
├── .env                      # Environment configuration
├── package.json (if applicable)  # Node.js dependencies
├── composer.json (if Laravel)    # PHP dependencies
└── pyproject.toml (if Python)    # Python dependencies
```

---

## Framework-Specific Guides

### Laravel Deep Dive
For detailed Laravel 12 setup with Livewire and Filament, see the original Laravel sections in this guide.

### Astro + Sanity Guide
```bash
# Install Sanity CLI
npm install -g @sanity/cli

# Initialize Sanity project
sanity init

# Configure Astro for Sanity
npm install @sanity/client @sanity/image-url
```

### React + API Integration
```bash
# Install API client libraries
npm install @tanstack/react-query axios

# Install state management (if needed)
npm install zustand  # or redux toolkit
```

---

## Tips for Success

1. **Choose the right CLAUDE.md** for your primary framework
2. **Always review PRPs** before executing them
3. **Run validation commands** after each implementation
4. **Use version control** - commit after each successful PRP execution
5. **Test thoroughly** at each stage
6. **Let Context7 auto-detect** your technologies for better documentation
7. **Keep PRPs focused** - one major feature per PRP

---

## Troubleshooting

### Common Issues

**Claude Code not finding commands:**
```bash
# Ensure .claude directory is in project root
ls -la .claude/commands/
```

**CLAUDE.md not being used:**
```bash
# File must be named exactly "CLAUDE.md" in project root
ls -la CLAUDE.md
```

**Context7 not detecting framework:**
```bash
# Be more explicit in your PRP requests
/prp-base-create user authentication using Laravel 12 built-in auth
/prp-base-create blog components using Astro and TypeScript
```

**Validation failing:**
```bash
# Run individual validation commands based on your stack
# Laravel:
vendor/bin/pint; vendor/bin/phpstan analyse; php artisan test

# Astro/React:
npm run lint; npm run type-check; npm run test

# Python:
uv run ruff check --fix; uv run mypy .; uv run pytest tests/ -v
```

This setup process works for **any technology stack** and gives you a fully configured project with the PRPs framework ready for AI-assisted development with Context7 documentation integration!