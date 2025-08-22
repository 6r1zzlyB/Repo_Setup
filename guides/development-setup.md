# Development Environment Setup Guide

A comprehensive guide for setting up a consistent development environment with VS Code, Augment Code, MCP servers, and essential tools for modern development workflows.

**Author:** Matt S  
**Created:** 2025  
**License:** All Rights Reserved (see [../LICENSE](../LICENSE))

## 📋 Table of Contents

- [Core Development Stack](#core-development-stack)
- [VS Code Configuration](#vs-code-configuration)
- [Augment Code Setup](#augment-code-setup)
- [MCP Server Configuration](#mcp-server-configuration)
- [Language Support](#language-support)
- [Shell Environment](#shell-environment)
- [Project Structure Standards](#project-structure-standards)
- [Development Workflow](#development-workflow)
- [Troubleshooting](#troubleshooting)
- [Maintenance](#maintenance)

## 🎯 Core Development Stack

### Primary Tools

- **Editor**: Visual Studio Code
- **AI Assistant**: Augment Code
- **Primary Shells**: PowerShell, Bash
- **Version Control**: Git
- **Package Managers**: pip (Python), npm (JavaScript), Chocolatey/winget (Windows)

### Supported Languages & Formats

- **Scripting**: PowerShell, Windows PowerShell, Python, Bash, Shell Script, Batch
- **Data Formats**: Markdown, YAML, XML, TXT, JSON, INI, CONFIG
- **Web Technologies**: JavaScript, HTML, CSS
- **Configuration**: INI, CONFIG, TOML, ENV files, CONF

## 🛠️ VS Code Configuration

### Essential Extensions

#### Core Extensions

```json
{
  "recommendations": [
    // Language Support
    "ms-python.python",
    "ms-python.pylint",
    "ms-python.black-formatter",
    "ms-vscode.powershell",
    "mads-hartmann.bash-ide-vscode",

    // File Format Support
    "yzhang.markdown-all-in-one",
    "redhat.vscode-yaml",
    "dotjoshjohnson.xml",
    "ms-vscode.vscode-json",
    "dlech.ini",

    // Development Tools
    "ms-vscode.vscode-typescript-next",
    "esbenp.prettier-vscode",
    "ms-vscode.vscode-eslint",
    "streetsidesoftware.code-spell-checker",

    // Infrastructure & DevOps
    "ms-azuretools.vscode-docker",
    "ms-vscode-remote.remote-containers",
    "ms-vscode-remote.remote-ssh",
    "ms-kubernetes-tools.vscode-kubernetes-tools",
    "hashicorp.terraform",

    // Git & Version Control
    "eamodio.gitlens",
    "github.vscode-pull-request-github",

    // Productivity
    "ms-vscode-remote.remote-containers",
    "ms-vscode-remote.remote-wsl",
    "ms-vscode.remote-explorer",
    "formulahendry.terminal-manager",

    // Augment Integration
    "augmentcode.augment-vscode"
  ]
}
```

### Theme and UI Extensions

```json
{
  "ui-extensions": [
    "pkief.material-icon-theme",
    "github.github-vscode-theme",
    "ms-vscode.vscode-color-info",
    "oderwat.indent-rainbow",
    "ms-vscode.brackets-pair-colorizer"
  ]
}
```

### VS Code Settings

#### User Settings (`settings.json`)

```json
{
  // Editor Configuration
  "editor.fontSize": 14,
  "editor.fontFamily": "'Cascadia Code', 'Fira Code', Consolas, 'Courier New', monospace",
  "editor.fontLigatures": true,
  "editor.tabSize": 4,
  "editor.insertSpaces": true,
  "editor.wordWrap": "on",
  "editor.minimap.enabled": true,
  "editor.bracketPairColorization.enabled": true,
  "editor.formatOnSave": true,
  "editor.formatOnPaste": true,

  // File Handling
  "files.autoSave": "afterDelay",
  "files.autoSaveDelay": 1000,
  "files.trimTrailingWhitespace": true,
  "files.insertFinalNewline": true,
  "files.encoding": "utf8",
  "files.eol": "\n",

  // Terminal Configuration
  "terminal.integrated.defaultProfile.windows": "PowerShell",
  "terminal.integrated.defaultProfile.linux": "bash",
  "terminal.integrated.defaultProfile.osx": "zsh",
  "terminal.integrated.fontSize": 12,
  "terminal.integrated.fontFamily": "'Cascadia Code', 'SF Mono', Consolas",
  "terminal.integrated.copyOnSelection": true,
  "terminal.integrated.rightClickBehavior": "paste",

  // Language-Specific Settings
  "python.defaultInterpreterPath": "python",
  "python.formatting.provider": "black",
  "python.linting.enabled": true,
  "python.linting.pylintEnabled": true,
  "powershell.codeFormatting.preset": "OTBS",
  "powershell.integratedConsole.showOnStartup": false,

  // File Associations
  "files.associations": {
    "*.ps1": "powershell",
    "*.psm1": "powershell",
    "*.psd1": "powershell",
    "*.sh": "shellscript",
    "*.yaml": "yaml",
    "*.yml": "yaml",
    "*.toml": "toml",
    "*.env": "dotenv",
    "*.ini": "ini",
    "*.cfg": "ini",
    "*.config": "xml",
    "*.conf": "ini"
  },

  // Git Configuration
  "git.enableSmartCommit": true,
  "git.autofetch": true,
  "git.confirmSync": false,
  "gitlens.views.repositories.files.layout": "tree",

  // Workspace Settings
  "workbench.colorTheme": "GitHub Dark",
  "workbench.iconTheme": "material-icon-theme",
  "workbench.startupEditor": "welcomePageInEmptyWorkbench",

  // Security
  "security.workspace.trust.untrustedFiles": "prompt",
  "extensions.ignoreRecommendations": false,

  // Performance
  "search.exclude": {
    "**/node_modules": true,
    "**/bower_components": true,
    "**/.git": true,
    "**/dist": true,
    "**/build": true,
    "**/__pycache__": true,
    "**/*.pyc": true
  }
}
```

### Workspace Configuration

#### Standard `.vscode/settings.json` for Projects

```json
{
  "python.defaultInterpreterPath": "./venv/Scripts/python.exe",
  "python.terminal.activateEnvironment": true,
  "eslint.workingDirectories": ["./src"],
  "editor.rulers": [80, 120],
  "files.exclude": {
    "**/__pycache__": true,
    "**/*.pyc": true,
    "**/node_modules": true,
    "**/.git": true,
    "**/dist": true,
    "**/build": true
  }
}
```

#### Launch Configuration (`.vscode/launch.json`)

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Python: Current File",
      "type": "python",
      "request": "launch",
      "program": "${file}",
      "console": "integratedTerminal"
    },
    {
      "name": "PowerShell: Current File",
      "type": "PowerShell",
      "request": "launch",
      "script": "${file}",
      "console": "integratedTerminal"
    },
    {
      "name": "Node.js: Current File",
      "type": "node",
      "request": "launch",
      "program": "${file}",
      "console": "integratedTerminal"
    }
  ]
}
```

## 🤖 Augment Code Setup

### Installation & Configuration

#### Setup Process

1. Install Augment Code extension from VS Code marketplace
2. Sign in with your Augment account
3. Configure API keys and preferences
4. Set up MCP server integrations

#### Augment Settings

```json
{
  // Augment-specific settings
  "augment.autoSuggest": true,
  "augment.contextWindow": "large",
  "augment.codeGeneration.enabled": true,
  "augment.documentation.autoGenerate": true,
  "augment.mcp.enabledServers": [
    "github",
    "notion",
    "confluence",
    "sequential-thinking",
    "playwright",
    "context7",
    "serena",
    "bmad-method-docs",
    "fetch",
    "puppeteer"
  ]
}
```

### Usage Guidelines

#### Best Practices

- Use descriptive prompts for code generation
- Review all generated code before implementation
- Leverage MCP servers for context-aware suggestions
- Utilize documentation generation features
- Keep API usage within reasonable limits

#### Common Commands

```text
// Generate function documentation
@augment document-function

// Create unit tests
@augment generate-tests

// Explain complex code
@augment explain-code

// Refactor code
@augment refactor-code

// Generate commit messages
@augment generate-commit
```

## 🔌 MCP Server Configuration

### Overview of MCP Servers

| Server                  | Purpose                   | Primary Use Cases                           |
| ----------------------- | ------------------------- | ------------------------------------------- |
| **GitHub**              | Repository management     | Code reviews, issue tracking, PR management |
| **Notion**              | Knowledge management      | Documentation, project planning, notes      |
| **Confluence**          | Team documentation       | Wiki pages, technical specs, processes      |
| **Sequential Thinking** | Logical reasoning         | Complex problem solving, decision trees     |
| **Playwright**          | Web automation            | E2E testing, web scraping, UI testing       |
| **Context7**            | Context management        | Project context, file relationships         |
| **Serena**              | Development workflow      | Task management, development processes      |
| **BMAD-Method Docs**    | Methodology documentation | Best practices, standards, procedures       |
| **Fetch**               | HTTP requests             | API testing, data retrieval                 |
| **Puppeteer**           | Browser automation        | Web scraping, PDF generation, testing       |

### Configuration Files

#### MCP Server Configuration (`mcp-config.json`)

```json
{
  "servers": {
    "github": {
      "endpoint": "https://api.github.com",
      "authentication": {
        "type": "token",
        "token": "${GITHUB_TOKEN}"
      },
      "capabilities": ["repository-access", "issue-management", "pr-management"]
    },
    "notion": {
      "endpoint": "https://api.notion.com/v1",
      "authentication": {
        "type": "oauth",
        "token": "${NOTION_TOKEN}"
      },
      "capabilities": ["page-creation", "database-queries", "content-search"]
    },
    "confluence": {
      "endpoint": "${CONFLUENCE_URL}/rest/api",
      "authentication": {
        "type": "basic",
        "username": "${CONFLUENCE_USER}",
        "password": "${CONFLUENCE_TOKEN}"
      },
      "capabilities": ["page-management", "content-search", "space-access"]
    },
    "playwright": {
      "capabilities": ["browser-automation", "testing", "screenshot-capture"]
    },
    "puppeteer": {
      "capabilities": [
        "web-scraping",
        "pdf-generation",
        "performance-monitoring"
      ]
    }
  }
}
```

#### Environment Variables (`.env`)

```bash
# GitHub Configuration
GITHUB_TOKEN=your_github_token_here
GITHUB_USERNAME=your_username

# Notion Configuration
NOTION_TOKEN=your_notion_integration_token
NOTION_DATABASE_ID=your_database_id

# Confluence Configuration
CONFLUENCE_URL=https://your-company.atlassian.net
CONFLUENCE_USER=your_email@company.com
CONFLUENCE_TOKEN=your_api_token

# Augment Configuration
AUGMENT_API_KEY=your_augment_api_key
```

### MCP Server Management Scripts

#### MCP Server Management PowerShell

```powershell
# MCP Server Management Functions

function Start-MCPServers {
    param([string[]]$Servers = @("github", "notion", "confluence"))

    Write-Host "🚀 Starting MCP servers..." -ForegroundColor Green

    foreach ($Server in $Servers) {
        try {
            Write-Host "  Starting $Server server..." -ForegroundColor Cyan
            Start-Process -FilePath "mcp-cli" -ArgumentList "start", $Server -NoNewWindow
            Start-Sleep -Seconds 2
        }
        catch {
            Write-Warning "Failed to start $Server server: $($_.Exception.Message)"
        }
    }

    # Verify servers are running
    Test-MCPServers
}

function Test-MCPServers {
    Write-Host "🔍 Testing MCP server connectivity..." -ForegroundColor Yellow

    $Servers = @("github", "notion", "confluence", "sequential-thinking", "playwright", "context7", "serena", "bmad-method-docs", "fetch", "puppeteer")

    foreach ($Server in $Servers) {
        try {
            $Result = Invoke-RestMethod -Uri "http://localhost:8080/mcp/status/$Server" -Method GET -TimeoutSec 5
            if ($Result.status -eq "running") {
                Write-Host "  ✅ $Server: Running" -ForegroundColor Green
            } else {
                Write-Host "  ⚠️ $Server: $($Result.status)" -ForegroundColor Yellow
            }
        }
        catch {
            Write-Host "  ❌ $Server: Not responding" -ForegroundColor Red
        }
    }
}

function Stop-MCPServers {
    Write-Host "🛑 Stopping MCP servers..." -ForegroundColor Yellow

    try {
        Stop-Process -Name "mcp-server" -Force -ErrorAction SilentlyContinue
        Write-Host "  All MCP servers stopped" -ForegroundColor Green
    }
    catch {
        Write-Warning "Error stopping MCP servers: $($_.Exception.Message)"
    }
}

function Restart-MCPServers {
    Stop-MCPServers
    Start-Sleep -Seconds 3
    Start-MCPServers
}

function Get-MCPServerLogs {
    param([string]$Server = "all")

    $LogPath = "$env:USERPROFILE\.mcp\logs"

    if ($Server -eq "all") {
        Get-ChildItem -Path $LogPath -Filter "*.log" | ForEach-Object {
            Write-Host "=== $($_.Name) ===" -ForegroundColor Cyan
            Get-Content -Path $_.FullName -Tail 10
            Write-Host ""
        }
    } else {
        $LogFile = Join-Path $LogPath "$Server.log"
        if (Test-Path $LogFile) {
            Get-Content -Path $LogFile -Tail 20
        } else {
            Write-Warning "Log file not found for server: $Server"
        }
    }
}
```

---

**License:** All Rights Reserved - See [../LICENSE](../LICENSE) file for details.

**Author:** Matt S
**Repository:** [repo_setup](https://github.com/6r1zzlyB/repo_setup) (Private)
