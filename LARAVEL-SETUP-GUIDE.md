# Laravel 12 Project Setup with PRPs Framework

Complete step-by-step guide to set up a new Laravel 12 project using the PRPs-agentic-eng framework for AI-assisted development.

## Prerequisites

- PHP 8.3+
- Composer
- Node.js 18+
- Git
- Claude Code CLI
- Python 3.12+ with UV (optional, for Python runner)

---

## Stage 1: Project Foundation Setup

### 1.1 Create Project Directory
```bash
# Create your project directory
mkdir my-laravel-project
cd my-laravel-project

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

### 1.3 Setup Laravel-Specific CLAUDE.md
```bash
# Copy the Laravel-specific CLAUDE.md file
cp /path/to/PRPs-agentic-eng/claude_md_files/CLAUDE-LARAVEL-12.md ./CLAUDE.md

# Note: The file MUST be named exactly "CLAUDE.md" (not CLAUDE-LARAVEL-12.md)
```

### 1.4 Install Laravel 12 with Full Stack
```bash
# Create Laravel 12 project
composer create-project laravel/laravel . "^12.0" --prefer-dist

# Install essential Laravel packages
composer require laravel/sanctum laravel/tinker

# Install Livewire 3 and Filament 3
composer require livewire/livewire livewire/volt filament/filament

# Install UI component libraries
composer require livewire/flux robsontenorio/mary

# Install development and testing tools
composer require --dev laravel/pint pest/pest pest/pest-plugin-laravel
composer require --dev phpstan/phpstan larastan/larastan
composer require --dev laravel/telescope barryvdh/laravel-ide-helper

# Install additional recommended packages
composer require predis/predis laravel/horizon spatie/laravel-ignition
```

### 1.5 Setup Environment
```bash
# Copy environment file
cp .env.example .env

# Generate application key
php artisan key:generate

# Create SQLite database (or configure your preferred database)
touch database/database.sqlite

# Run initial migrations
php artisan migrate

# Install and build frontend assets
npm install
npm run build
```

### 1.6 Configure Filament Admin Panel
```bash
# Install Filament admin panel
php artisan filament:install --panels

# Create admin user
php artisan make:filament-user
```

### 1.7 Optional: Setup Python Environment (if using runner)
```bash
# Only if you want to use the Python PRP runner
curl -LsSf https://astral.sh/uv/install.sh | sh
uv venv
uv sync
```

---

## Stage 2: Project Planning Phase

### 2.1 Create Project Planning PRP
```bash
# Open Claude Code in your project directory
claude

# In Claude Code, run the planning command with your project requirements
/prp-planning-create [your-project-description]

# Example:
/prp-planning-create compliance accreditation assessment system for children suppliers with multi-form workflows and file uploads
```

**What happens:**
- Claude generates a comprehensive planning document
- Auto-saves to `PRPs/{project-name}-planning-{YYYY-MM-DD}.md`
- Contains project scope, user stories, technical architecture, database design
- Includes implementation phases and roadmap

### 2.2 Review Planning PRP
```bash
# Review the generated planning PRP
cat PRPs/*-planning-*.md

# Edit if needed
nano PRPs/*-planning-*.md
```

---

## Stage 3: Implementation PRP Creation

Based on your planning PRP, create focused implementation PRPs for each major component:

### 3.1 Create Database & Models PRP
```bash
# In Claude Code
/prp-base-create user management system with compliance and accreditation tracking

# This auto-saves to: PRPs/user-management-{date}.md
```

### 3.2 Create Authentication PRP
```bash
/prp-base-create Laravel authentication system with Sanctum API and Livewire components

# Auto-saves to: PRPs/laravel-authentication-{date}.md
```

### 3.3 Create Form System PRP
```bash
/prp-base-create multi-step Livewire forms with file uploads and weighted scoring

# Auto-saves to: PRPs/multi-step-forms-{date}.md
```

### 3.4 Create Filament Admin PRP
```bash
/prp-base-create Filament admin panel with user management and application tracking

# Auto-saves to: PRPs/filament-admin-{date}.md
```

### 3.5 Review Generated PRPs
```bash
# List all generated PRPs
ls -la PRPs/*.md

# Review each PRP before execution
cat PRPs/user-management-*.md
cat PRPs/laravel-authentication-*.md
# etc.
```

---

## Stage 4: Code Implementation

### 4.1 Execute PRPs in Dependency Order

Execute PRPs in logical order based on dependencies:

#### 4.1.1 Start with Database & Models
```bash
# In Claude Code
/execute-base-prp PRPs/user-management-[date].md
```

**What happens:**
- Claude creates migration files
- Creates Eloquent models with relationships
- Sets up enums for status tracking
- Creates model factories and seeders
- Runs validation tests

#### 4.1.2 Setup Authentication
```bash
/execute-base-prp PRPs/laravel-authentication-[date].md
```

**What happens:**
- Configures Laravel Sanctum
- Creates authentication controllers
- Sets up API routes
- Creates authentication tests

#### 4.1.3 Build Form System
```bash
/execute-base-prp PRPs/multi-step-forms-[date].md
```

**What happens:**
- Creates Livewire form components
- Implements file upload handling
- Adds validation and scoring logic
- Creates form templates and styling

#### 4.1.4 Setup Admin Panel
```bash
/execute-base-prp PRPs/filament-admin-[date].md
```

**What happens:**
- Creates Filament resources
- Sets up admin dashboard
- Configures user management interface
- Adds reporting and analytics

### 4.2 Validation After Each PRP
```bash
# Run validation commands after each PRP execution
vendor/bin/pint
vendor/bin/phpstan analyse
php artisan test --coverage

# Fix any issues before proceeding to next PRP
```

---

## Stage 5: Testing & Quality Assurance

### 5.1 Run Full Test Suite
```bash
# Run all tests with coverage
php artisan test --coverage

# Run static analysis
vendor/bin/phpstan analyse --level=8

# Run code formatting
vendor/bin/pint

# Generate IDE helper files
php artisan ide-helper:generate
php artisan ide-helper:models
php artisan ide-helper:meta
```

### 5.2 Setup Development Environment
```bash
# Start development servers (run in separate terminals)
php artisan serve              # Laravel app
php artisan queue:work         # Queue processing
npm run dev                    # Vite asset building
php artisan horizon           # Queue dashboard (if using Redis)
```

### 5.3 Test Application Features
```bash
# Test API endpoints
curl -X POST http://localhost:8000/api/register \
  -H "Content-Type: application/json" \
  -d '{"name":"Test User","email":"test@example.com","password":"password123"}'

# Access admin panel
open http://localhost:8000/admin

# Test Livewire components
open http://localhost:8000
```

---

## Stage 6: Production Preparation

### 6.1 Environment Configuration
```bash
# Update .env for production
cp .env.example .env.production

# Configure production database
# Configure mail settings
# Configure file storage
# Configure cache/session drivers
```

### 6.2 Security Hardening
```bash
# Clear and cache configuration
php artisan config:cache
php artisan route:cache
php artisan view:cache

# Run security checks
composer audit

# Generate API keys
php artisan tinker
# Generate your API keys and tokens
```

### 6.3 Performance Optimization
```bash
# Install opcache
# Configure Redis
# Set up queue workers
# Configure file storage (S3, etc.)

# Test performance
# Run load tests if needed
```

---

## Stage 7: Deployment

### 7.1 Build Production Assets
```bash
# Build optimized assets
npm run build

# Clear all caches
php artisan optimize:clear
php artisan optimize
```

### 7.2 Database Migration
```bash
# Run migrations on production
php artisan migrate --force

# Seed production data if needed
php artisan db:seed --class=ProductionSeeder
```

---

## Quick Reference Commands

### PRP Management
```bash
# Create planning PRP
/prp-planning-create [project-description]

# Create implementation PRP
/prp-base-create [feature-description]

# Execute PRP
/execute-base-prp PRPs/[prp-file].md

# List PRPs
ls -la PRPs/*.md
```

### Laravel Development
```bash
# Validation commands
vendor/bin/pint && vendor/bin/phpstan analyse && php artisan test

# Development servers
php artisan serve
php artisan queue:work
npm run dev

# Clear caches
php artisan optimize:clear

# Generate IDE helpers
php artisan ide-helper:generate
```

### Optional Python Runner Commands
```bash
# If using Python runner
uv run PRPs/scripts/prp_runner.py --prp [prp-name] --interactive
uv run PRPs/scripts/prp_runner.py --prp [prp-name] --output-format json
```

---

## File Structure After Setup

```
my-laravel-project/
├── .claude/                  # Claude Code commands (copied from framework)
│   ├── commands/            # 28+ Claude commands
│   └── settings.local.json  # Tool permissions
├── PRPs/                    # PRP files (copied from framework)
│   ├── templates/          # PRP templates
│   ├── scripts/           # Python runner (optional)
│   ├── ai_docs/           # AI documentation
│   ├── *-planning-*.md    # Generated planning PRPs
│   └── *-*.md             # Generated implementation PRPs
├── CLAUDE.md               # Laravel-specific guidance (renamed)
├── app/                    # Laravel application
│   ├── Livewire/          # Livewire components
│   ├── Filament/          # Filament admin resources
│   ├── Models/            # Eloquent models
│   └── Services/          # Business logic services
├── database/              # Migrations, factories, seeders
├── tests/                 # Test files
├── composer.json          # PHP dependencies
├── package.json           # Node.js dependencies
└── pyproject.toml         # Python dependencies (optional)
```

---

## Tips for Success

1. **Always review PRPs** before executing them
2. **Run validation commands** after each implementation
3. **Follow the dependency order** when executing PRPs
4. **Use version control** - commit after each successful PRP execution
5. **Test thoroughly** at each stage
6. **Customize the planning PRP** with your specific requirements
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

**Validation failing:**
```bash
# Run individual validation commands
vendor/bin/pint
vendor/bin/phpstan analyse
php artisan test
```

**Python runner not working:**
```bash
# Check UV installation
uv --version
# Check Python environment
uv run python --version
```

This setup process will give you a fully configured Laravel 12 project with the PRPs framework ready for AI-assisted development!