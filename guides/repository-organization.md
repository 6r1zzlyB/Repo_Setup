# Repository Organization Guide

Comprehensive guide for organizing GitHub repositories following modern best practices, including file structure, naming conventions, and GitHub-specific features for personal projects.

**Author:** Matt S  
**Created:** 2025  
**License:** All Rights Reserved (see [../LICENSE](../LICENSE))

## 📋 Table of Contents

1. [Repository Structure Standards](#-repository-structure-standards)
2. [Essential Files](#-essential-files)
3. [Directory Organization](#-directory-organization)
4. [Naming Conventions](#-naming-conventions)
5. [GitHub Features](#-github-features)
6. [Security Configuration](#-security-configuration)
7. [Development Workflow](#-development-workflow)
8. [Maintenance Guidelines](#-maintenance-guidelines)

## 🏗️ Repository Structure Standards

### Standard Repository Layout

```text
repository-name/
├── README.md                    # Project overview and documentation
├── LICENSE                      # License terms and conditions
├── CHANGELOG.md                 # Version history and changes
├── .gitignore                   # Git ignore patterns
├── .env.example                 # Environment variable template
├── requirements.txt             # Python dependencies (if applicable)
├── package.json                 # Node.js dependencies (if applicable)
├── .vscode/                     # VS Code workspace configuration
│   ├── settings.json            # Workspace-specific settings
│   ├── extensions.json          # Recommended extensions
│   └── launch.json              # Debug configurations
├── .github/                     # GitHub-specific files
│   ├── workflows/               # GitHub Actions workflows
│   ├── ISSUE_TEMPLATE/          # Issue templates
│   └── PULL_REQUEST_TEMPLATE.md # Pull request template
├── docs/                        # Additional documentation
│   ├── api/                     # API documentation
│   ├── guides/                  # User guides and tutorials
│   └── assets/                  # Documentation assets (images, etc.)
├── src/                         # Source code (language-specific)
│   ├── main/                    # Main application code
│   ├── test/                    # Test files
│   └── resources/               # Application resources
├── scripts/                     # Utility and build scripts
│   ├── build/                   # Build scripts
│   ├── deploy/                  # Deployment scripts
│   └── maintenance/             # Maintenance utilities
├── config/                      # Configuration files
│   ├── development/             # Development environment config
│   ├── staging/                 # Staging environment config
│   └── production/              # Production environment config
└── assets/                      # Static assets and resources
    ├── images/                  # Image files
    ├── fonts/                   # Font files
    └── data/                    # Data files and samples
```

### Language-Specific Variations

#### Python Projects

```text
python-project/
├── README.md
├── LICENSE
├── CHANGELOG.md
├── .gitignore
├── requirements.txt             # Production dependencies
├── requirements-dev.txt         # Development dependencies
├── setup.py                     # Package setup configuration
├── pyproject.toml              # Modern Python project configuration
├── src/
│   └── package_name/
│       ├── __init__.py
│       ├── main.py
│       └── modules/
├── tests/
│   ├── __init__.py
│   ├── test_main.py
│   └── fixtures/
├── docs/
└── scripts/
```

#### JavaScript/Node.js Projects

```text
javascript-project/
├── README.md
├── LICENSE
├── CHANGELOG.md
├── .gitignore
├── package.json                 # Dependencies and scripts
├── package-lock.json           # Dependency lock file
├── .eslintrc.js                # ESLint configuration
├── .prettierrc                 # Prettier configuration
├── src/
│   ├── index.js
│   ├── components/
│   └── utils/
├── test/
├── dist/                       # Built/compiled files
├── public/                     # Public assets
└── docs/
```

#### PowerShell Projects

```text
powershell-project/
├── README.md
├── LICENSE
├── CHANGELOG.md
├── .gitignore
├── module-name.psd1            # Module manifest
├── module-name.psm1            # Module file
├── src/
│   ├── Public/                 # Public functions
│   ├── Private/                # Private functions
│   └── Classes/                # PowerShell classes
├── tests/
│   └── Pester/                 # Pester test files
├── docs/
│   └── help/                   # PowerShell help files
└── scripts/
    ├── build.ps1
    └── publish.ps1
```

## 📄 Essential Files

### Required Files

#### README.md

- **Purpose**: Primary project documentation and entry point
- **Location**: Repository root
- **Content**: Follow [Documentation Standards](documentation-standards.md)
- **Maintenance**: Update with every major change

#### LICENSE

- **Purpose**: Legal terms for code usage and distribution
- **Location**: Repository root
- **Content**: "All Rights Reserved" for personal projects
- **Format**: Plain text file

#### .gitignore

- **Purpose**: Specify files Git should ignore
- **Location**: Repository root
- **Content**: Language-specific and environment-specific patterns
- **Maintenance**: Update when adding new tools or dependencies

### Recommended Files

#### CHANGELOG.md

- **Purpose**: Track version history and changes
- **Location**: Repository root
- **Format**: Follow [Keep a Changelog](https://keepachangelog.com/) format
- **Maintenance**: Update with every release

#### .env.example

- **Purpose**: Template for environment variables
- **Location**: Repository root
- **Content**: Example values with descriptions
- **Security**: Never include actual secrets or API keys

### Development Files

#### .vscode/settings.json

```json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.organizeImports": true
  },
  "python.defaultInterpreterPath": "./venv/Scripts/python.exe",
  "files.exclude": {
    "**/__pycache__": true,
    "**/*.pyc": true,
    "**/node_modules": true,
    "**/.git": true
  }
}
```

#### .vscode/extensions.json

```json
{
  "recommendations": [
    "ms-python.python",
    "ms-vscode.powershell",
    "yzhang.markdown-all-in-one",
    "streetsidesoftware.code-spell-checker",
    "augmentcode.augment-vscode"
  ]
}
```

## 📁 Directory Organization

### Source Code Organization

#### Hierarchical Structure

- **src/**: Main source code directory
  - **main/**: Primary application code
  - **test/**: Test files and test utilities
  - **resources/**: Configuration files, data files, assets

#### Modular Organization

- Group related functionality together
- Use clear, descriptive directory names
- Maintain consistent depth (avoid deep nesting)
- Separate public and private interfaces

### Documentation Organization

#### docs/ Directory Structure

```text
docs/
├── README.md                   # Documentation index
├── getting-started.md          # Quick start guide
├── installation.md             # Installation instructions
├── configuration.md            # Configuration guide
├── api/                        # API documentation
│   ├── README.md
│   ├── endpoints.md
│   └── examples.md
├── guides/                     # User guides
│   ├── basic-usage.md
│   ├── advanced-features.md
│   └── troubleshooting.md
├── development/                # Developer documentation
│   ├── contributing.md
│   ├── architecture.md
│   └── testing.md
└── assets/                     # Documentation assets
    ├── images/
    ├── diagrams/
    └── screenshots/
```

### Configuration Management

#### Environment-Specific Configuration

```text
config/
├── default.json                # Default configuration
├── development.json            # Development overrides
├── staging.json                # Staging environment
├── production.json             # Production environment
└── local.json                  # Local development (gitignored)
```

#### Security Considerations

- Never commit sensitive configuration
- Use environment variables for secrets
- Provide example configurations
- Document all configuration options

## 🏷️ Naming Conventions

### Repository Names

#### Format Guidelines

- Use lowercase letters and hyphens
- Be descriptive but concise
- Avoid abbreviations unless widely understood
- Use consistent naming patterns

#### Examples

```text
✅ Good Examples:
- user-management-system
- data-processing-pipeline
- api-documentation-generator
- powershell-utility-scripts

❌ Avoid:
- UMS (unclear abbreviation)
- my_project (underscores)
- DataProcessingPipeline (camelCase)
- project1 (non-descriptive)
```

### File and Directory Names

#### General Rules

- Use lowercase for directories
- Use descriptive names that indicate purpose
- Be consistent within the project
- Follow language-specific conventions

#### Language-Specific Conventions

**Python:**
- Files: `snake_case.py`
- Directories: `lowercase` or `snake_case`
- Modules: `snake_case`

**JavaScript:**
- Files: `camelCase.js` or `kebab-case.js`
- Directories: `lowercase` or `kebab-case`
- Components: `PascalCase.js`

**PowerShell:**
- Files: `PascalCase.ps1`
- Functions: `Verb-Noun` format
- Modules: `PascalCase.psm1`

### Branch Names

#### Naming Pattern

```text
<type>/<description>

Types:
- feature/    # New features
- fix/        # Bug fixes
- hotfix/     # Critical fixes
- docs/       # Documentation updates
- refactor/   # Code refactoring
- test/       # Test additions/updates
```

#### Examples

```text
feature/user-authentication
fix/memory-leak-in-processor
hotfix/security-vulnerability
docs/api-documentation-update
refactor/database-connection-logic
test/integration-test-suite
```

## 🐙 GitHub Features

### Repository Settings

#### General Settings

- **Repository name**: Follow naming conventions
- **Description**: Clear, concise project description
- **Website**: Link to documentation or live demo
- **Topics**: Relevant tags for discoverability
- **Visibility**: Private for personal projects, public for open source

#### Features Configuration

```text
✅ Enable:
- Issues (for bug tracking and feature requests)
- Projects (for project management)
- Wiki (for extended documentation)
- Discussions (for community interaction)

⚠️ Consider:
- Sponsorships (for open source projects)
- Security advisories (for public projects)
```

### Branch Protection Rules

#### Main Branch Protection

```text
Protection Rules for 'main' branch:
✅ Require pull request reviews before merging
✅ Require status checks to pass before merging
✅ Require branches to be up to date before merging
✅ Require conversation resolution before merging
✅ Restrict pushes that create files over 100MB
✅ Allow force pushes (for personal repos)
✅ Allow deletions (with caution)
```

#### Development Branch Strategy

```text
Branch Strategy:
- main: Production-ready code
- develop: Integration branch for features
- feature/*: Individual feature development
- hotfix/*: Critical production fixes
- release/*: Release preparation
```

### Issue Templates

#### Bug Report Template (`.github/ISSUE_TEMPLATE/bug_report.md`)

```markdown
---
name: Bug Report
about: Create a report to help improve the project
title: '[BUG] '
labels: bug
assignees: 6r1zzlyB
---

## Bug Description

A clear and concise description of what the bug is.

## Steps to Reproduce

1. Go to '...'
2. Click on '....'
3. Scroll down to '....'
4. See error

## Expected Behavior

A clear and concise description of what you expected to happen.

## Actual Behavior

A clear and concise description of what actually happened.

## Environment

- OS: [e.g. Windows 10, macOS 11.0, Ubuntu 20.04]
- Version: [e.g. 1.2.3]
- Browser: [if applicable]

## Additional Context

Add any other context about the problem here.
```

#### Feature Request Template (`.github/ISSUE_TEMPLATE/feature_request.md`)

```markdown
---
name: Feature Request
about: Suggest an idea for this project
title: '[FEATURE] '
labels: enhancement
assignees: 6r1zzlyB
---

## Feature Description

A clear and concise description of what you want to happen.

## Problem Statement

A clear and concise description of what the problem is. Ex. I'm always frustrated when [...]

## Proposed Solution

A clear and concise description of what you want to happen.

## Alternative Solutions

A clear and concise description of any alternative solutions or features you've considered.

## Additional Context

Add any other context or screenshots about the feature request here.
```

### Pull Request Template

#### `.github/PULL_REQUEST_TEMPLATE.md`

```markdown
## Description

Brief description of changes and motivation.

## Type of Change

- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update
- [ ] Code refactoring
- [ ] Performance improvement

## Testing

- [ ] Unit tests pass
- [ ] Integration tests pass
- [ ] Manual testing completed
- [ ] No breaking changes introduced

## Checklist

- [ ] Code follows project style guidelines
- [ ] Self-review of code completed
- [ ] Code is commented, particularly in hard-to-understand areas
- [ ] Corresponding changes to documentation made
- [ ] No new warnings introduced
- [ ] Tests added that prove fix is effective or feature works

## Related Issues

Closes #(issue number)
```

### GitHub Actions Workflows

#### Basic CI Workflow (`.github/workflows/ci.yml`)

```yaml
name: Continuous Integration

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3

    - name: Set up Python
      uses: actions/setup-python@v4
      with:
        python-version: '3.9'

    - name: Install dependencies
      run: |
        python -m pip install --upgrade pip
        pip install -r requirements.txt
        pip install -r requirements-dev.txt

    - name: Run tests
      run: |
        python -m pytest tests/ --cov=src/ --cov-report=xml

    - name: Upload coverage to Codecov
      uses: codecov/codecov-action@v3
      with:
        file: ./coverage.xml
```

## 🔒 Security Configuration

### Repository Security Settings

#### Security Features

```text
✅ Enable:
- Vulnerability alerts
- Automated security fixes
- Dependency graph
- Code scanning alerts
- Secret scanning alerts

⚠️ Configure:
- Security policy (SECURITY.md)
- Private vulnerability reporting
- Security advisories
```

### Security Policy Template

#### `SECURITY.md`

```markdown
# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| 1.x.x   | :white_check_mark: |
| < 1.0   | :x:                |

## Reporting a Vulnerability

If you discover a security vulnerability, please report it responsibly:

1. **Do not** open a public issue
2. Email security details to: [your-email@domain.com]
3. Include steps to reproduce and potential impact
4. Allow reasonable time for response and fix

## Security Best Practices

- Keep dependencies updated
- Use environment variables for sensitive data
- Enable two-factor authentication
- Review code changes carefully
- Monitor security alerts
```

### Secrets Management

#### Environment Variables

```bash
# Repository Secrets (GitHub Settings > Secrets)
API_KEY=your_api_key_here
DATABASE_URL=your_database_url
DEPLOYMENT_TOKEN=your_deployment_token

# Environment Variables in Actions
env:
  API_KEY: ${{ secrets.API_KEY }}
  DATABASE_URL: ${{ secrets.DATABASE_URL }}
```

#### .env.example Template

```bash
# API Configuration
API_KEY=your_api_key_here
API_URL=https://api.example.com

# Database Configuration
DATABASE_URL=postgresql://user:password@localhost:5432/dbname
DATABASE_POOL_SIZE=10

# Application Configuration
DEBUG=false
LOG_LEVEL=info
PORT=3000

# External Services
REDIS_URL=redis://localhost:6379
SMTP_HOST=smtp.example.com
SMTP_PORT=587
SMTP_USER=your_email@example.com
SMTP_PASS=your_email_password
```

---

**License:** All Rights Reserved - See [../LICENSE](../LICENSE) file for details.

**Author:** Matt S
**Repository:** [repo_setup](https://github.com/6r1zzlyB/repo_setup) (Private)
