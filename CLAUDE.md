# Project Configuration for Claude

This file contains project-specific context, conventions, and guidelines that Claude should follow when working with this codebase.

## Project Overview

This is the **Repository Setup Template & Style Guide** - a personal template for creating well-organized, professional GitHub repositories. It provides templates, documentation standards, and development environment configuration.

**Author:** Matthew Stdenis
**License:** All Rights Reserved (Confidential)

## Code Style Guidelines

### General Standards

- Use 4-space indentation for all files (consistent with VS Code settings)
- Maximum line length: 120 characters
- Use UTF-8 encoding for all files
- Files should end with a newline
- Trim trailing whitespace

### Markdown Standards

- Use ATX-style headers (`#`, `##`, `###`)
- Use fenced code blocks with language identifiers
- Use bullet lists (`-`) for unordered lists
- Use numbered lists (`1.`, `2.`, etc.) for sequential steps
- Include alt text for images
- Use reference-style links for repeated URLs

### YAML Standards

- Use 2-space indentation
- Quote strings containing special characters
- Use lowercase keys with hyphens for multi-word keys

### JSON Standards

- Use 2-space indentation
- Always use double quotes for keys and string values
- No trailing commas

### PowerShell Standards

- Use PascalCase for function names (Verb-Noun format)
- Use camelCase for variables
- Use OTBS (One True Brace Style) formatting
- Include comment-based help for functions

### Python Standards

- Follow PEP 8 style guide
- Use Black formatter with default settings
- Use type hints for function signatures
- Maximum line length: 88 characters (Black default)

## Documentation Standards

### Content Types

When creating documentation, use appropriate content types:

- **Conceptual** - Explains what and why
- **Referential** - Comprehensive details and specifications
- **Procedural** - Step-by-step instructions
- **Troubleshooting** - Solutions for common problems
- **Quickstart** - Fast path to get started
- **Tutorial** - Learning-oriented guidance

### Writing Principles

- Start with user needs and goals
- Use clear headings and bullet points
- Prefer plain language over jargon
- Use active voice
- Keep sentences concise

### Visual Documentation

Use Mermaid diagrams with consistent color scheme:
- Input/Start: `#c8e6c9` (light green)
- Process/Action: `#e1f5fe` (light blue)
- Decision/Logic: `#f3e5f5` (light purple)
- Output/Storage: `#fff3e0` (light orange)
- Error/Warning: `#ffcdd2` (light red)

## Repository Structure

```
repo_setup/
├── README.md                   # Project overview
├── LICENSE                     # License terms
├── CHANGELOG.md                # Version history
├── CLAUDE.md                   # Claude configuration (this file)
├── .serena/                    # Serena configuration
├── mise.toml                   # Mise tool configuration
├── .github/                    # GitHub-specific files
├── templates/                  # Ready-to-use templates
├── guides/                     # Documentation guides
└── examples/                   # Example implementations
```

## Common Commands

```bash
# Git Operations
git status                      # Check repository status
git add .                       # Stage all changes
git commit -m "type: message"   # Commit with conventional message

# Development
code .                          # Open in VS Code
```

## Commit Message Convention

Use conventional commit format:

```
type(scope): description

[optional body]

[optional footer]
```

Types:
- `feat` - New feature
- `fix` - Bug fix
- `docs` - Documentation changes
- `style` - Code style changes (formatting, etc.)
- `refactor` - Code refactoring
- `test` - Adding or updating tests
- `chore` - Maintenance tasks

## Security Guidelines

- Never commit `.env` files or credentials
- Keep sensitive projects private by default
- Use environment variables for secrets
- Review code before committing
- Enable GitHub security alerts

## AI Assistant Guidelines

When working on this codebase:

1. Follow existing patterns in templates and guides
2. Maintain consistent formatting across all documentation
3. Use the established Mermaid color scheme for diagrams
4. Respect the confidential nature of this repository
5. Check for existing templates before creating new files
6. Follow the documentation standards outlined in `guides/documentation-standards.md`
7. Keep README headers consistent with `guides/readme-header-standards.md`
