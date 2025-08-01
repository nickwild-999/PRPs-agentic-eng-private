# CLAUDE.md

This file provides comprehensive guidance to Claude Code when working with Laravel 12 applications with Livewire 3 and Filament 3.

## Core Development Philosophy

### KISS (Keep It Simple, Stupid)

Simplicity should be a key goal in design. Choose straightforward solutions over complex ones whenever possible. Simple solutions are easier to understand, maintain, and debug.

### YAGNI (You Aren't Gonna Need It)

Avoid building functionality on speculation. Implement features only when they are needed, not when you anticipate they might be useful in the future.

### Design Principles (MUST FOLLOW)

- **Vertical Slice Architecture**: MUST organize by features, not layers
- **Dependency Injection**: MUST use Laravel's container for all dependencies
- **Fail Fast**: MUST validate inputs early with Form Requests, throw exceptions immediately
- **Convention over Configuration**: Follow Laravel conventions consistently
- **Single Responsibility**: Each class, method, and service should have one clear purpose
- **Reactive Components**: Use Livewire for interactive UI without complex JavaScript

## 🤖 AI Assistant Guidelines

### Context Awareness

- When implementing features, always check existing patterns first
- Use Laravel's built-in features before creating custom solutions
- Check for similar functionality in other domains/features
- Follow established Laravel conventions and patterns
- Prefer Livewire components over traditional controllers for interactive UIs

### Common Pitfalls to Avoid

- Creating duplicate functionality
- Overwriting existing tests
- Modifying core Laravel files without explicit instruction
- Adding dependencies without checking existing alternatives
- Ignoring Laravel naming conventions
- Mixing business logic in Livewire components

### Workflow Patterns

- Preferably create tests BEFORE implementation (TDD)
- Use "think hard" for architecture decisions
- Break complex tasks into smaller, testable units
- Validate understanding before implementation

### Search Command Requirements

**CRITICAL**: Always use `rg` (ripgrep) instead of traditional `grep` and `find` commands:

```bash
# ❌ Don't use grep
grep -r "pattern" .

# ✅ Use rg instead
rg "pattern"

# ❌ Don't use find with name
find . -name "*.php"

# ✅ Use rg with file filtering
rg --files | rg "\.php$"
# or
rg --files -g "*.php"
```

## 🚀 Laravel 12, Livewire 3 & Filament 3 Key Features

### Laravel 12 Core Features

- **PHP 8.3+ Support**: Modern PHP features and performance improvements
- **Enhanced Eloquent**: Improved query builder and ORM features
- **Advanced Queues**: Better job management and processing
- **Improved Testing**: Enhanced testing utilities and performance
- **Security Enhancements**: Stronger authentication and authorization
- **Performance Optimizations**: Faster routing and middleware processing

### Livewire 3 Features

- **Reactive Components**: Real-time UI updates without JavaScript
- **Volt**: File-based component syntax for rapid development
- **Alpine.js Integration**: Enhanced client-side interactivity
- **Wire Navigate**: SPA-like navigation with full-page Livewire
- **Lazy Loading**: Improved performance with deferred component loading
- **Event System**: Powerful component communication

### Filament 3 Features

- **Admin Panel**: Complete admin interface with zero configuration
- **Form Builder**: Powerful form creation with validation
- **Table Builder**: Advanced data tables with filtering and sorting
- **Notification System**: Toast notifications and database notifications
- **Dashboard Widgets**: Customizable dashboard components
- **Multi-tenancy**: Built-in support for multi-tenant applications

### PHP Integration (MANDATORY)

- **MUST use strict types** in ALL PHP files: `declare(strict_types=1);`
- **MUST use proper type hints** for all parameters and return types
- **MUST use union types and nullable types** appropriately
- **NEVER use mixed type** unless absolutely necessary with documentation

```php
<?php

declare(strict_types=1);

namespace App\Livewire;

use Livewire\Component;
use Livewire\Attributes\Validate;

// ✅ CORRECT: Modern Livewire 3 component
final class UserProfile extends Component
{
    #[Validate('required|string|min:2')]
    public string $name = '';
    
    #[Validate('required|email')]
    public string $email = '';
    
    public function save(): void
    {
        $this->validate();
        // Save logic
    }
    
    public function render(): \Illuminate\View\View
    {
        return view('livewire.user-profile');
    }
}

// ❌ FORBIDDEN: No strict types or proper typing
class UserProfile extends Component
{
    public $name;
    public $email;
    
    public function save()
    {
        // Implementation
    }
}
```

## 🏗️ Project Structure (Vertical Slice Architecture)

```
app/
├── Console/               # Artisan commands
│   └── Commands/
├── Exceptions/           # Custom exception classes
├── Filament/             # Filament admin panel (MANDATORY)
│   ├── Resources/        # Filament resources
│   ├── Pages/            # Custom Filament pages
│   ├── Widgets/          # Dashboard widgets
│   └── Clusters/         # Resource clusters
├── Http/
│   ├── Controllers/      # HTTP controllers (thin layer)
│   ├── Middleware/       # HTTP middleware
│   ├── Requests/         # Form request validation (MANDATORY)
│   └── Resources/        # API resources
├── Livewire/             # Livewire components (MANDATORY)
│   ├── Components/       # Reusable Livewire components
│   ├── Pages/            # Full-page Livewire components
│   ├── Forms/            # Form-specific components
│   └── Actions/          # Action components (logout, etc.)
├── Models/               # Eloquent models
├── Providers/            # Service providers
├── Services/             # Business logic layer (MANDATORY)
├── Repositories/         # Data access layer (when needed)
├── Policies/             # Authorization policies
├── Events/               # Event classes
├── Listeners/            # Event listeners
├── Jobs/                 # Queue jobs
├── Mail/                 # Mailable classes
├── Notifications/        # Notification classes
└── Features/             # Feature-based modules (RECOMMENDED)
    └── [feature]/
        ├── Livewire/     # Feature Livewire components
        ├── Filament/     # Feature Filament resources
        ├── Services/     # Feature services
        ├── Models/       # Feature models
        ├── Tests/        # Co-located tests (MANDATORY)
        └── routes.php    # Feature routes

resources/
├── views/
│   ├── livewire/         # Livewire component views
│   ├── components/       # Blade components
│   └── layouts/          # Layout files
├── css/                  # Styling files
└── js/                   # JavaScript files

database/
├── factories/            # Model factories
├── migrations/           # Database migrations
└── seeders/             # Database seeders
```

## 🎯 PHP & Laravel Configuration (STRICT REQUIREMENTS)

### Essential Laravel 12 Dependencies

```json
{
  "require": {
    "php": "^8.3",
    "laravel/framework": "^12.0",
    "livewire/livewire": "^3.6",
    "livewire/volt": "^1.7.0",
    "filament/filament": "^3.2",
    "laravel/sanctum": "^4.0",
    "laravel/tinker": "^2.10"
  },
  "require-dev": {
    "phpunit/phpunit": "^11.0",
    "laravel/pint": "^1.18",
    "pest/pest": "^3.8",
    "pest/pest-plugin-laravel": "^3.1",
    "nunomaduro/collision": "^8.6",
    "laravel/sail": "^1.41",
    "phpstan/phpstan": "^1.10",
    "larastan/larastan": "^2.9"
  }
}
```

### Recommended Additional Dependencies

```bash
# UI Components and Styling
composer require livewire/flux robsontenorio/mary

# Admin Panel (Filament ecosystem)
composer require filament/spatie-laravel-media-library-plugin
composer require filament/spatie-laravel-settings-plugin
composer require filament/spatie-laravel-translatable-plugin

# Development and Testing Tools
composer require --dev laravel/telescope barryvdh/laravel-ide-helper
composer require --dev spatie/laravel-ignition mockery/mockery

# Performance and Caching
composer require predis/predis laravel/horizon
```

### MANDATORY Type Requirements

- **MUST use strict types** in ALL PHP files: `declare(strict_types=1);`
- **MUST use proper type hints** for all parameters and return types
- **MUST use union types and nullable types** appropriately
- **NEVER use mixed type** unless absolutely necessary with documentation
- **MUST use enum classes** for constants and status values

```php
<?php

declare(strict_types=1);

namespace App\Services;

use App\Models\User;
use App\Enums\UserStatus;
use App\Exceptions\ValidationException;

/**
 * User management service handling registration and profile updates.
 * 
 * This service encapsulates all business logic related to user operations,
 * ensuring data integrity and business rule enforcement.
 * 
 * @package App\Services
 */
final readonly class UserService
{
    public function __construct(
        private UserRepository $userRepository,
        private NotificationService $notificationService,
    ) {}

    /**
     * Create a new user with validation and business logic.
     * 
     * @param array<string, mixed> $userData
     * @throws ValidationException When user data is invalid
     */
    public function createUser(array $userData): User
    {
        // Validation and business logic
        $this->validateUserData($userData);
        
        $user = $this->userRepository->create($userData);
        
        // Fire events
        event(new UserRegistered($user));
        
        return $user;
    }
    
    private function validateUserData(array $data): void
    {
        // Custom business validation beyond form requests
        if ($this->userRepository->existsByEmail($data['email'])) {
            throw new ValidationException('Email already exists');
        }
    }
}
```

## 🛡️ Request Validation (MANDATORY FOR ALL INPUTS)

### MUST Follow These Validation Rules

- **MUST use Form Requests** for ALL HTTP input validation
- **MUST validate at the boundary** - never trust incoming data
- **MUST use Laravel's validation rules** with custom rules when needed
- **MUST return meaningful error messages** for API consumers
- **NEVER validate in controllers** - use Form Requests exclusively

### Form Request Example (MANDATORY PATTERN)

```php
<?php

declare(strict_types=1);

namespace App\Http\Requests;

use Illuminate\Foundation\Http\FormRequest;
use Illuminate\Validation\Rule;
use App\Enums\UserRole;

/**
 * Validation rules for user registration requests.
 * 
 * Handles all input validation and sanitization for user creation,
 * including business rule validation and error message customization.
 * 
 * @package App\Http\Requests
 */
final class CreateUserRequest extends FormRequest
{
    /**
     * Determine if the user is authorized to make this request.
     */
    public function authorize(): bool
    {
        return true; // Handle authorization in policies
    }

    /**
     * Get the validation rules that apply to the request.
     * 
     * @return array<string, mixed>
     */
    public function rules(): array
    {
        return [
            'name' => ['required', 'string', 'max:255', 'min:2'],
            'email' => [
                'required',
                'email:rfc,dns',
                'max:255',
                Rule::unique('users', 'email'),
            ],
            'password' => [
                'required',
                'string',
                'min:8',
                'confirmed',
                'regex:/^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]/',
            ],
            'role' => ['required', Rule::enum(UserRole::class)],
            'birth_date' => ['required', 'date', 'before:today', 'after:1900-01-01'],
            'terms_accepted' => ['required', 'accepted'],
        ];
    }

    /**
     * Get custom error messages for validation rules.
     * 
     * @return array<string, string>
     */
    public function messages(): array
    {
        return [
            'password.regex' => 'Password must contain at least one uppercase letter, one lowercase letter, one number, and one special character.',
            'birth_date.before' => 'You must be born before today.',
            'birth_date.after' => 'Please enter a valid birth date.',
        ];
    }

    /**
     * Get custom attribute names for error messages.
     * 
     * @return array<string, string>
     */
    public function attributes(): array
    {
        return [
            'birth_date' => 'date of birth',
            'terms_accepted' => 'terms and conditions',
        ];
    }
}
```

## 🎨 Livewire Component Guidelines (STRICT REQUIREMENTS)

### MANDATORY Livewire Component Documentation

```php
<?php

declare(strict_types=1);

namespace App\Livewire\Components;

use Livewire\Component;
use Livewire\Attributes\Validate;
use Livewire\Attributes\On;
use App\Services\ContactService;

/**
 * Contact modal component for handling user inquiries.
 * 
 * Provides a reusable modal with form validation and email sending.
 * Supports event-driven communication with parent components.
 * 
 * @package App\Livewire\Components
 * 
 * @example
 * ```blade
 * <livewire:contact-modal />
 * 
 * <!-- Trigger modal -->
 * <button wire:click="$dispatch('open-contact-modal', { page: 'home' })">
 *     Contact Us
 * </button>
 * ```
 */
final class ContactModal extends Component
{
    /** Whether the modal is currently visible */
    public bool $showModal = false;
    
    /** Company name from the form */
    #[Validate('required|string|min:2|max:255')]
    public string $companyName = '';
    
    /** Contact person's name */
    #[Validate('required|string|min:2|max:255')]
    public string $contactName = '';
    
    /** Email address for contact */
    #[Validate('required|email|max:255')]
    public string $email = '';
    
    /** Phone number with flexible format validation */
    #[Validate('required|string|regex:/^[\+]?[\d\s\-\(\)]{7,20}$/')]
    public string $phone = '';
    
    /** Optional message from the user */
    #[Validate('nullable|string|max:1000')]
    public string $message = '';
    
    /** Current page where modal was opened */
    public string $currentPage = '';
    
    public function __construct(
        private readonly ContactService $contactService
    ) {}
    
    /**
     * Open the contact modal.
     * 
     * @param string $page The page where modal was triggered
     */
    #[On('open-contact-modal')]
    public function openModal(string $page = ''): void
    {
        $this->currentPage = $page ?: request()->fullUrl();
        $this->showModal = true;
    }
    
    /**
     * Close the modal and reset form data.
     */
    public function closeModal(): void
    {
        $this->showModal = false;
        $this->reset(['companyName', 'contactName', 'email', 'phone', 'message', 'currentPage']);
    }
    
    /**
     * Submit the contact form.
     * 
     * Validates input, sends emails, and provides user feedback.
     * Dispatches events for analytics and user experience.
     */
    public function submit(): void
    {
        $this->validate();
        
        $contactData = [
            'company_name' => $this->companyName,
            'contact_name' => $this->contactName,
            'email' => $this->email,
            'phone' => $this->phone,
            'message' => $this->message,
            'source_page' => $this->currentPage,
        ];
        
        // Process through service layer
        $this->contactService->processContactSubmission($contactData);
        
        // User feedback
        session()->flash('success', 'Thank you! Your inquiry has been submitted.');
        
        // Dispatch events for analytics
        $this->dispatch('contact-submitted', [
            'source_page' => $this->currentPage,
            'company_name' => $this->companyName,
        ]);
        
        $this->closeModal();
    }
    
    /**
     * Render the component view.
     */
    public function render(): \Illuminate\View\View
    {
        return view('livewire.components.contact-modal');
    }
}
```

### Livewire Component Best Practices (MANDATORY)

- **MAXIMUM 200 lines** per component class
- **MUST use dependency injection** for services
- **MUST delegate business logic** to services
- **MUST use Attributes for validation** (#[Validate])
- **MUST use event system** for component communication
- **NEVER put business logic** in component methods
- **MUST handle ALL states**: loading, error, empty, and success

## 🎯 Filament Admin Panel (MANDATORY FOR ADMIN INTERFACES)

### Filament Resource Pattern (MANDATORY)

```php
<?php

declare(strict_types=1);

namespace App\Filament\Resources;

use App\Filament\Resources\UserResource\Pages;
use App\Models\User;
use App\Enums\UserRole;
use App\Enums\UserStatus;
use Filament\Forms\Form;
use Filament\Forms\Components\TextInput;
use Filament\Forms\Components\Select;
use Filament\Forms\Components\Toggle;
use Filament\Resources\Resource;
use Filament\Tables\Table;
use Filament\Tables\Columns\TextColumn;
use Filament\Tables\Columns\IconColumn;
use Filament\Tables\Actions\EditAction;
use Filament\Tables\Actions\DeleteAction;
use Filament\Tables\Filters\SelectFilter;
use Illuminate\Database\Eloquent\Builder;

/**
 * User resource for Filament admin panel.
 * 
 * Provides CRUD interface for user management with proper validation,
 * authorization, and bulk operations. Includes advanced filtering and search.
 * 
 * @package App\Filament\Resources
 */
final class UserResource extends Resource
{
    protected static ?string $model = User::class;
    
    protected static ?string $navigationIcon = 'heroicon-o-users';
    
    protected static ?string $navigationGroup = 'User Management';
    
    protected static ?int $navigationSort = 1;
    
    /**
     * Define the form schema for creating/editing users.
     */
    public static function form(Form $form): Form
    {
        return $form
            ->schema([
                TextInput::make('name')
                    ->required()
                    ->maxLength(255)
                    ->helperText('Full name of the user'),
                    
                TextInput::make('email')
                    ->email()
                    ->required()
                    ->unique(User::class, 'email', ignoreRecord: true)
                    ->maxLength(255),
                    
                Select::make('role')
                    ->options(UserRole::class)
                    ->required()
                    ->helperText('User role determines permissions'),
                    
                Select::make('status')
                    ->options(UserStatus::class)
                    ->required()
                    ->default(UserStatus::ACTIVE),
                    
                Toggle::make('email_verified')
                    ->label('Email Verified')
                    ->helperText('Whether the user has verified their email address'),
            ]);
    }
    
    /**
     * Define the table schema for listing users.
     */
    public static function table(Table $table): Table
    {
        return $table
            ->columns([
                TextColumn::make('name')
                    ->searchable()
                    ->sortable(),
                    
                TextColumn::make('email')
                    ->searchable()
                    ->sortable()
                    ->copyable(),
                    
                TextColumn::make('role')
                    ->badge()
                    ->sortable(),
                    
                TextColumn::make('status')
                    ->badge()
                    ->color(fn (UserStatus $state): string => match ($state) {
                        UserStatus::ACTIVE => 'success',
                        UserStatus::INACTIVE => 'warning',
                        UserStatus::SUSPENDED => 'danger',
                    }),
                    
                IconColumn::make('email_verified_at')
                    ->label('Verified')
                    ->boolean()
                    ->trueIcon('heroicon-o-check-badge')
                    ->falseIcon('heroicon-o-x-mark'),
                    
                TextColumn::make('created_at')
                    ->dateTime()
                    ->sortable()
                    ->toggleable(isToggledHiddenByDefault: true),
            ])
            ->filters([
                SelectFilter::make('role')
                    ->options(UserRole::class),
                    
                SelectFilter::make('status')
                    ->options(UserStatus::class),
            ])
            ->actions([
                EditAction::make(),
                DeleteAction::make()
                    ->requiresConfirmation(),
            ])
            ->bulkActions([
                // Bulk actions here
            ]);
    }
    
    /**
     * Get the pages associated with this resource.
     */
    public static function getPages(): array
    {
        return [
            'index' => Pages\ListUsers::route('/'),
            'create' => Pages\CreateUser::route('/create'),
            'edit' => Pages\EditUser::route('/{record}/edit'),
        ];
    }
    
    /**
     * Modify the Eloquent query for this resource.
     */
    public static function getEloquentQuery(): Builder
    {
        return parent::getEloquentQuery()
            ->withoutGlobalScopes();
    }
}
```

## 🧪 Testing Strategy (MANDATORY REQUIREMENTS)

### MUST Meet These Testing Standards

- **MINIMUM 80% code coverage** - NO EXCEPTIONS
- **MUST co-locate tests** with features in appropriate directories
- **MUST use Pest PHP** for all new tests (Laravel 12 default)
- **MUST test behavior** not implementation details
- **MUST mock external dependencies** appropriately
- **NEVER skip tests** for new features or bug fixes

### Pest PHP Configuration (MANDATORY)

```php
<?php

declare(strict_types=1);

// tests/Pest.php
use Tests\TestCase;
use Illuminate\Foundation\Testing\RefreshDatabase;

uses(TestCase::class)->in('Feature');
uses(TestCase::class)->in('Unit');

/**
 * Create an authenticated user for testing.
 */
function actingAsUser(string $role = 'user'): \App\Models\User
{
    $user = \App\Models\User::factory()->create(['role' => $role]);
    test()->actingAs($user);
    return $user;
}

/**
 * Assert JSON response structure for API tests.
 */
function assertApiResponse(array $structure): \Pest\Expectation
{
    return expect(response()->json())->toMatchArray($structure);
}
```

### Livewire Testing Example

```php
<?php

declare(strict_types=1);

use App\Livewire\ContactModal;
use App\Services\ContactService;
use Illuminate\Foundation\Testing\RefreshDatabase;
use Livewire\Livewire;

uses(RefreshDatabase::class);

/**
 * Test suite for ContactModal Livewire component.
 */
describe('ContactModal', function () {
    beforeEach(function () {
        $this->contactService = Mockery::mock(ContactService::class);
        app()->instance(ContactService::class, $this->contactService);
    });

    it('opens modal when event is dispatched', function () {
        Livewire::test(ContactModal::class)
            ->dispatch('open-contact-modal', page: 'home')
            ->assertSet('showModal', true)
            ->assertSet('currentPage', 'home');
    });

    it('validates required fields on submit', function () {
        Livewire::test(ContactModal::class)
            ->call('submit')
            ->assertHasErrors([
                'companyName' => 'required',
                'contactName' => 'required',
                'email' => 'required',
                'phone' => 'required',
            ]);
    });

    it('submits form with valid data', function () {
        $this->contactService
            ->shouldReceive('processContactSubmission')
            ->once()
            ->andReturn(true);

        Livewire::test(ContactModal::class)
            ->set('companyName', 'Test Company')
            ->set('contactName', 'John Doe')
            ->set('email', 'john@example.com')
            ->set('phone', '+1234567890')
            ->set('message', 'Test message')
            ->call('submit')
            ->assertSet('showModal', false)
            ->assertDispatched('contact-submitted');
    });
});
```

## 🔐 Security Requirements (MANDATORY)

### Authentication & Authorization (MUST IMPLEMENT ALL)

- **MUST use Laravel Sanctum** for API authentication
- **MUST implement proper CSRF protection** for web routes
- **MUST use Policies** for all authorization logic
- **MUST validate all inputs** with Form Requests
- **NEVER store passwords in plain text**
- **MUST implement rate limiting** for sensitive endpoints

### Policy Example (MANDATORY PATTERN)

```php
<?php

declare(strict_types=1);

namespace App\Policies;

use App\Models\User;
use App\Enums\UserRole;

/**
 * User authorization policy.
 * 
 * Defines authorization rules for user-related operations.
 * Separates authorization logic from controllers and services.
 * 
 * @package App\Policies
 */
final class UserPolicy
{
    /**
     * Determine whether the user can view any users.
     */
    public function viewAny(User $user): bool
    {
        return $user->role === UserRole::ADMIN || $user->role === UserRole::MANAGER;
    }

    /**
     * Determine whether the user can view the model.
     */
    public function view(User $user, User $model): bool
    {
        // Users can view their own profile
        if ($user->id === $model->id) {
            return true;
        }

        // Admins and managers can view all users
        return $user->role === UserRole::ADMIN || $user->role === UserRole::MANAGER;
    }

    /**
     * Determine whether the user can create users.
     */
    public function create(User $user): bool
    {
        return $user->role === UserRole::ADMIN;
    }

    /**
     * Determine whether the user can update the model.
     */
    public function update(User $user, User $model): bool
    {
        // Users can update their own profile (limited fields)
        if ($user->id === $model->id) {
            return true;
        }

        // Admins can update any user
        return $user->role === UserRole::ADMIN;
    }

    /**
     * Determine whether the user can delete the model.
     */
    public function delete(User $user, User $model): bool
    {
        // Users cannot delete themselves
        if ($user->id === $model->id) {
            return false;
        }

        // Only admins can delete users
        return $user->role === UserRole::ADMIN;
    }
}
```

## 🚀 Performance Guidelines

### Database Optimization (MANDATORY)

- **MUST use database indexes** for frequently queried columns
- **MUST use Eloquent relationships** instead of manual joins
- **MUST implement query optimization** with eager loading
- **MUST use database transactions** for data consistency
- **NEVER use N+1 queries** - always eager load relationships

### Livewire Performance (MANDATORY)

- **MUST use lazy loading** for heavy components
- **MUST implement proper caching** for expensive operations
- **MUST use wire:key** for dynamic lists
- **NEVER load large datasets** in component properties
- **MUST use pagination** for large result sets

## 💅 Code Style & Quality

### Laravel Pint Configuration (MANDATORY)

```json
{
    "preset": "laravel",
    "rules": {
        "declare_strict_types": true,
        "binary_operator_spaces": {
            "default": "single_space"
        },
        "blank_line_after_opening_tag": true,
        "class_definition": {
            "single_line": true
        },
        "no_unused_imports": true,
        "ordered_imports": {
            "sort_algorithm": "alpha"
        },
        "phpdoc_align": true,
        "phpdoc_separation": true,
        "return_type_declaration": true,
        "single_quote": true,
        "trailing_comma_in_multiline": {
            "elements": ["arrays"]
        }
    }
}
```

## 📋 Development Commands

```json
{
  "scripts": {
    "dev": [
      "Composer\\Config::disableProcessTimeout",
      "npx concurrently -c \"#93c5fd,#c4b5fd,#fb7185,#fdba74\" \"php artisan serve\" \"php artisan queue:listen --tries=1\" \"php artisan pail --timeout=0\" \"npm run dev\" --names=server,queue,logs,vite"
    ],
    "fresh": "php artisan migrate:fresh --seed",
    "test": "php artisan test",
    "test-coverage": "php artisan test --coverage",
    "test-parallel": "php artisan test --parallel",
    "pint": "vendor/bin/pint",
    "pint-check": "vendor/bin/pint --test",
    "stan": "vendor/bin/phpstan analyse",
    "ide-helper": "php artisan ide-helper:generate && php artisan ide-helper:models && php artisan ide-helper:meta",
    "queue": "php artisan queue:work",
    "horizon": "php artisan horizon",
    "schedule": "php artisan schedule:work",
    "filament-upgrade": "php artisan filament:upgrade",
    "optimize": "php artisan optimize && php artisan config:cache && php artisan route:cache && php artisan view:cache",
    "optimize-clear": "php artisan optimize:clear",
    "validate": "composer pint-check && composer stan && php artisan test --coverage"
  }
}
```

## ⚠️ CRITICAL GUIDELINES (MUST FOLLOW ALL)

1. **ENFORCE strict PHP typing** - ZERO compromises on type safety
2. **VALIDATE everything with Form Requests** - ALL user inputs must be validated
3. **MINIMUM 80% test coverage** - NO EXCEPTIONS
4. **MUST co-locate tests** with features in appropriate directories
5. **MAXIMUM 500 lines per file** - Split if larger
6. **MAXIMUM 200 lines per Livewire component** - Extract services if larger
7. **MUST handle ALL states** in Livewire - Loading, error, empty, and success
8. **MUST use semantic commits** - feat:, fix:, docs:, refactor:, test:
9. **MUST write complete PHPDoc** - ALL classes and methods must be documented
10. **MUST use Services** for business logic - Components and controllers should be thin
11. **MUST implement Filament resources** with proper authorization policies
12. **MUST pass ALL automated checks** - Before ANY merge

## 📋 Pre-commit Checklist (MUST COMPLETE ALL)

- [ ] PHP syntax valid (`php -l` on all files)
- [ ] Laravel Pint formatting applied (`vendor/bin/pint`)
- [ ] PHPStan analysis passes (`vendor/bin/phpstan analyse`)
- [ ] Tests written and passing with 80%+ coverage (`php artisan test --coverage`)
- [ ] All Form Requests have complete validation rules
- [ ] All Livewire components use Services for business logic
- [ ] All services have complete PHPDoc documentation
- [ ] All policies are implemented for authorization
- [ ] Database migrations are reversible
- [ ] No sensitive data in version control
- [ ] Environment variables properly validated
- [ ] Filament resources return consistent structure
- [ ] Rate limiting implemented for sensitive endpoints
- [ ] All Eloquent relationships properly defined
- [ ] Cache invalidation strategies implemented
- [ ] Event listeners are properly registered
- [ ] Livewire components handle all UI states

### FORBIDDEN Practices

- **NEVER put business logic** in Livewire components or controllers
- **NEVER skip validation** for user inputs - always use Form Requests
- **NEVER ignore PHPStan errors** or disable strict mode
- **NEVER store passwords in plain text**
- **NEVER use raw SQL** without proper escaping or query builder
- **NEVER skip tests** for new functionality
- **NEVER commit** without passing all quality checks
- **NEVER use `mixed` type** without comprehensive documentation
- **NEVER access request data** outside of Form Requests or Livewire validation
- **NEVER implement authorization** in controllers - use Policies
- **NEVER skip database transactions** for multi-step operations
- **NEVER use global variables** or static state in Livewire components
- **NEVER hardcode configuration values** - use config files and .env
- **NEVER expose internal errors** to users - log and show user-friendly messages
- **NEVER create Filament resources** without proper authorization policies
- **NEVER use Livewire components** for complex business logic - delegate to services
- **NEVER mix presentation and business logic** in Livewire components
- **NEVER forget wire:key** for dynamic Livewire lists
- **NEVER load large datasets** directly in Livewire component properties

---

## 📝 Recent Updates

### January 2025 - Laravel 12 with Livewire 3 and Filament 3

Comprehensive Laravel 12 guidance covering:

- **Livewire 3 Integration**: Modern reactive components with attributes-based validation
- **Filament 3 Admin Panel**: Complete admin interface with resources, forms, and tables
- **PHP 8.3+ Strict Typing**: Mandatory strict types, proper type hints, enum classes
- **Service-Oriented Architecture**: Business logic separation from presentation layer
- **Advanced Validation**: Form Requests with comprehensive validation rules
- **Security-First Approach**: Sanctum authentication, policy-based authorization, rate limiting
- **Testing Excellence**: Pest PHP integration, 80% coverage requirement, Livewire testing
- **Performance Optimization**: Database optimization, Livewire lazy loading, caching strategies
- **Code Quality Enforcement**: Laravel Pint, PHPStan level 8, comprehensive documentation

These guidelines ensure production-ready Laravel applications with modern reactive UIs and comprehensive admin interfaces.

---

*This guide is optimized for Laravel 12 with Livewire 3 and Filament 3. Keep it updated as frameworks evolve.*
*Focus on type safety, security, performance, and maintainability in all development decisions.*
*Last updated: January 2025*