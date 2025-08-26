# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a **repository setup template and style guide** for creating well-organized, professional GitHub repositories. It serves as both a template source and documentation standard reference for personal projects.

**Key Purpose**: Provides ready-to-use templates, development standards, and comprehensive documentation guidelines for consistent repository organization across all personal projects.

## Architecture & Structure

### High-Level Organization

```
repo_setup/
├── templates/           # Ready-to-use templates for new projects
│   ├── README_TEMPLATE.md      # Comprehensive README template
│   ├── CHANGELOG_TEMPLATE.md   # Semantic versioning changelog
│   └── PROJECT_STRUCTURE.md    # Standard directory layouts
├── guides/             # Comprehensive documentation standards
│   ├── development-setup.md         # VS Code, Augment, MCP setup
│   ├── documentation-standards.md   # README/changelog standards
│   ├── readme-header-standards.md   # Standardized headers
│   └── repository-organization.md   # GitHub best practices
└── examples/           # Example implementations and workflows
```

### Content Architecture

This repository follows a **three-tier content model**:

1. **Templates** (`/templates/`) - Direct-use files that can be copied to new projects
2. **Guides** (`/guides/`) - Comprehensive standards and setup documentation  
3. **Examples** (`/examples/`) - Reference implementations and workflow examples

### Documentation Standards Framework

The guides establish a comprehensive documentation system with:

- **Standardized README structure** with required sections and formatting
- **Semantic versioning changelog format** following Keep a Changelog standards
- **Visual documentation standards** using Mermaid diagrams with consistent color schemes
- **Professional header format** with badges, licensing, and confidentiality notices

### Development Environment Integration

The development setup guide configures a modern development stack:
- **VS Code** as primary editor with comprehensive extension recommendations
- **Augment Code** for AI-powered development assistance
- **MCP servers** for context-aware development tools (GitHub, Notion, Confluence, Sequential Thinking, Playwright, Context7, Serena, etc.)
- **Cross-platform compatibility** for Windows, macOS, and Linux

## Working with This Repository

### Common Development Tasks

**No build/test/lint commands** - This is a documentation and template repository without executable code.

### Key Usage Patterns

1. **Creating New Projects**: Copy templates from `/templates/` directory
2. **Updating Standards**: Modify guides in `/guides/` directory  
3. **Repository Auditing**: Use standards from guides to review existing projects
4. **Development Setup**: Follow `/guides/development-setup.md` for environment configuration

### File Modification Guidelines

**When updating templates**:
- Maintain placeholder format `[placeholder-text]` for customizable content
- Keep consistent badge structure in README headers
- Preserve license and confidentiality notices
- Update examples to reflect current best practices

**When updating guides**:
- Maintain comprehensive section structure 
- Update version numbers and tool recommendations
- Keep Mermaid diagram color schemes consistent (`#c8e6c9` for inputs, `#e1f5fe` for processes, etc.)
- Validate all cross-references and links

### Key Configuration Details

**MCP Server Integration**: The development setup includes configuration for 10+ MCP servers with specific capabilities:
- GitHub (repository management)
- Notion/Confluence (knowledge management) 
- Sequential Thinking (logical reasoning)
- Playwright (web automation)
- Context7 (project context)
- Serena (development workflow)

**VS Code Configuration**: Comprehensive settings for multi-language support (PowerShell, Python, Bash, JavaScript, Markdown, YAML, XML) with formatting, linting, and debugging configurations.

**Documentation Color Standards**: Visual documentation uses standardized Mermaid color scheme for consistency across all diagrams and architectural representations.

## Important Notes

- **Confidential Repository**: All content marked as "All Rights Reserved" and intended for personal use only
- **Template-Based Workflow**: This repository serves as the source of truth for personal project standards
- **Cross-Platform Standards**: All configurations and standards designed to work across Windows, macOS, and Linux
- **AI Development Integration**: Heavily integrated with Augment Code and MCP servers for AI-assisted development workflows