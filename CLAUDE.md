# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Laravel package skeleton template for PHP development. It's designed to be a starting point for creating reusable PHP packages with modern development tools and best practices.

## Key Development Commands

### Testing

```bash
composer test              # Run all tests using Pest
```

### Code Quality

```bash
composer lint              # Run code formatting (Pint) and static analysis (PHPStan)
composer build            # Build the workbench environment
composer serve            # Start development server
```

### Environment Setup

```bash
composer install          # Install PHP dependencies
pnpm install              # Install Node.js dependencies (for linting tools)
```

## Project Structure

### Core Directories

- `src/` - Main package source code (PSR-4 autoload: `Yuxin\SkeletonPhp\`)
- `tests/` - Test suite with Pest (PSR-4 autoload: `Tests\`)
- `workbench/` - Laravel testing environment for package development
- `config/` - Configuration files
- `database/` - Database migrations and seeds

### Key Files

- `src/helpers.php` - Global helper functions (auto-loaded)
- `tests/TestCase.php` - Base test class
- `tests/Pest.php` - Pest configuration and custom test helpers

## Development Tools

### Code Style & Quality

- **Laravel Pint**: Code formatting and style fixing
  - Config: `pint.json`
  - Preset: Laravel with strict type declarations
- **PHPStan**: Static code analysis
  - Config: `phpstan.neon.dist`
  - Level: 5 (medium strictness)
  - Analyzes: `src/` directory

### Testing Framework

- **Pest**: Modern PHP testing framework
- **PHPUnit**: Traditional PHPUnit fallback
- **Orchestra Testbench**: Laravel package testing environment
- Test categories:
  - `tests/Feature/` - Integration/feature tests
  - `tests/Unit/` - Unit tests

### Git Hooks

- **Husky** + **lint-staged**: Pre-commit hooks
  - Runs Pint and PHPStan on PHP files
  - Runs Prettier on other file types
  - Config: `lint-staged.config.mjs`

## Workbench Environment

The `workbench/` directory provides a complete Laravel application for testing your package:

- **App**: `workbench/app/` - Example application structure
- **Database**: `workbench/database/` - Test database setup
- **Routes**: `workbench/routes/` - Web and API routes
- **Resources**: `workbench/resources/` - Views and assets

## Code Standards

### PHP Requirements

- PHP 8.4+
- Strict types enabled (`declare(strict_types=1)`)
- PSR-4 autoloading
- Laravel coding conventions

### Pint Rules

- Laravel preset with customizations:
- Strict type declarations
- Fully qualified imports
- Ordered class elements
- Strict comparisons
- Single trait per statement

### Testing Best Practices

- Write tests in Pest syntax
- Use `Tests\TestCase` as base class
- Separate unit and feature tests
- Follow Laravel testing conventions

## Package Development

When creating a new package from this skeleton:

1. Update `composer.json` with your package details
2. Change PSR-4 namespace in `autoload` section
3. Update package name and description
4. Configure `testbench.yaml` for your package requirements
5. Add your service providers to workbench configuration

## Dependencies

### PHP Development Dependencies

- `laravel/pint` - Code formatting
- `orchestra/testbench` - Laravel package testing
- `pestphp/pest` - Modern testing framework
- `phpstan/phpstan` - Static analysis

### Node.js Dependencies

- `husky` - Git hooks
- `lint-staged` - Pre-commit linting
- `prettier` - Code formatting (non-PHP files)

## Naming Conventions

- Namespace: `Yuxin\SkeletonPhp\`
- Package name: `zhaiyuxin/skeleton-php`
- Test namespace: `Tests\`
- Workbench namespace: `Workbench\`

## Configuration Files

- `testbench.yaml` - Testbench configuration
- `phpstan.neon.dist` - PHPStan settings
- `pint.json` - Code style rules
- `phpunit.xml` - PHPUnit configuration
- `composer.json` - Package configuration and scripts
