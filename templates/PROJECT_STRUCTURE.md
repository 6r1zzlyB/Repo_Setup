# Project Structure Templates

Standard directory layouts and file organization patterns for different types of projects, ensuring consistency and maintainability across all personal repositories.

**Author:** Matt S  
**Created:** 2025  
**License:** All Rights Reserved (see [../LICENSE](../LICENSE))

## 📋 Table of Contents

1. [General Purpose Projects](#-general-purpose-projects)
2. [Python Projects](#-python-projects)
3. [JavaScript/Node.js Projects](#-javascriptnodejs-projects)
4. [PowerShell Projects](#-powershell-projects)
5. [Web Applications](#-web-applications)
6. [API Projects](#-api-projects)
7. [Documentation Projects](#-documentation-projects)
8. [Utility Scripts](#-utility-scripts)

## 🏗️ General Purpose Projects

### Basic Project Structure

```text
project-name/
├── README.md                    # Project documentation
├── LICENSE                      # License file
├── CHANGELOG.md                 # Version history
├── .gitignore                   # Git ignore patterns
├── .env.example                 # Environment variables template
├── .vscode/                     # VS Code configuration
│   ├── settings.json            # Workspace settings
│   ├── extensions.json          # Recommended extensions
│   └── launch.json              # Debug configurations
├── .github/                     # GitHub-specific files
│   ├── workflows/               # GitHub Actions
│   ├── ISSUE_TEMPLATE/          # Issue templates
│   └── PULL_REQUEST_TEMPLATE.md # PR template
├── docs/                        # Documentation
│   ├── README.md                # Documentation index
│   ├── installation.md          # Installation guide
│   ├── usage.md                 # Usage instructions
│   └── assets/                  # Images, diagrams
├── src/                         # Source code
├── tests/                       # Test files
├── scripts/                     # Utility scripts
├── config/                      # Configuration files
└── assets/                      # Static assets
```

### Essential Files Content

#### .gitignore (General)

```gitignore
# OS generated files
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

# IDE files
.vscode/
.idea/
*.swp
*.swo
*~

# Environment files
.env
.env.local
.env.*.local

# Logs
logs
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# Runtime data
pids
*.pid
*.seed
*.pid.lock

# Temporary folders
tmp/
temp/

# Build outputs
dist/
build/
out/
```

## 🐍 Python Projects

### Python Project Structure

```text
python-project/
├── README.md
├── LICENSE
├── CHANGELOG.md
├── .gitignore                   # Python-specific ignore patterns
├── requirements.txt             # Production dependencies
├── requirements-dev.txt         # Development dependencies
├── setup.py                     # Package setup (legacy)
├── pyproject.toml              # Modern Python configuration
├── setup.cfg                   # Setup configuration
├── MANIFEST.in                 # Package manifest
├── .env.example
├── .vscode/
│   ├── settings.json
│   └── launch.json
├── src/
│   └── package_name/
│       ├── __init__.py
│       ├── main.py
│       ├── cli.py              # Command-line interface
│       ├── config.py           # Configuration handling
│       ├── exceptions.py       # Custom exceptions
│       ├── utils.py            # Utility functions
│       └── modules/
│           ├── __init__.py
│           ├── core.py
│           └── helpers.py
├── tests/
│   ├── __init__.py
│   ├── conftest.py             # Pytest configuration
│   ├── test_main.py
│   ├── test_cli.py
│   ├── unit/                   # Unit tests
│   ├── integration/            # Integration tests
│   └── fixtures/               # Test fixtures
├── docs/
│   ├── conf.py                 # Sphinx configuration
│   ├── index.rst
│   └── api/
├── scripts/
│   ├── build.py
│   ├── test.py
│   └── deploy.py
└── data/                       # Data files
    ├── raw/
    ├── processed/
    └── external/
```

### Python Configuration Files

#### pyproject.toml

```toml
[build-system]
requires = ["setuptools>=45", "wheel", "setuptools_scm[toml]>=6.2"]
build-backend = "setuptools.build_meta"

[project]
name = "package-name"
description = "Package description"
readme = "README.md"
requires-python = ">=3.8"
license = {text = "All Rights Reserved"}
authors = [
    {name = "Matt S", email = "your-email@domain.com"},
]
classifiers = [
    "Development Status :: 4 - Beta",
    "Intended Audience :: Developers",
    "Programming Language :: Python :: 3",
    "Programming Language :: Python :: 3.8",
    "Programming Language :: Python :: 3.9",
    "Programming Language :: Python :: 3.10",
    "Programming Language :: Python :: 3.11",
]
dependencies = [
    "requests>=2.25.0",
    "click>=8.0.0",
]
dynamic = ["version"]

[project.optional-dependencies]
dev = [
    "pytest>=6.0",
    "pytest-cov>=2.0",
    "black>=21.0",
    "flake8>=3.8",
    "mypy>=0.800",
]

[project.scripts]
package-name = "package_name.cli:main"

[tool.setuptools_scm]

[tool.black]
line-length = 88
target-version = ['py38']

[tool.pytest.ini_options]
testpaths = ["tests"]
python_files = ["test_*.py"]
python_classes = ["Test*"]
python_functions = ["test_*"]
addopts = "--cov=src --cov-report=html --cov-report=term-missing"
```

#### .gitignore (Python)

```gitignore
# Byte-compiled / optimized / DLL files
__pycache__/
*.py[cod]
*$py.class

# C extensions
*.so

# Distribution / packaging
.Python
build/
develop-eggs/
dist/
downloads/
eggs/
.eggs/
lib/
lib64/
parts/
sdist/
var/
wheels/
*.egg-info/
.installed.cfg
*.egg
MANIFEST

# PyInstaller
*.manifest
*.spec

# Installer logs
pip-log.txt
pip-delete-this-directory.txt

# Unit test / coverage reports
htmlcov/
.tox/
.nox/
.coverage
.coverage.*
.cache
nosetests.xml
coverage.xml
*.cover
.hypothesis/
.pytest_cache/

# Virtual environments
.env
.venv
env/
venv/
ENV/
env.bak/
venv.bak/

# Jupyter Notebook
.ipynb_checkpoints

# IPython
profile_default/
ipython_config.py

# pyenv
.python-version

# Spyder project settings
.spyderproject
.spyproject

# Rope project settings
.ropeproject

# mkdocs documentation
/site

# mypy
.mypy_cache/
.dmypy.json
dmypy.json
```

## 📜 JavaScript/Node.js Projects

### Node.js Project Structure

```text
nodejs-project/
├── README.md
├── LICENSE
├── CHANGELOG.md
├── .gitignore
├── package.json                 # Dependencies and scripts
├── package-lock.json           # Dependency lock file
├── .nvmrc                      # Node version specification
├── .eslintrc.js                # ESLint configuration
├── .prettierrc                 # Prettier configuration
├── jest.config.js              # Jest testing configuration
├── .env.example
├── .vscode/
├── src/
│   ├── index.js                # Main entry point
│   ├── app.js                  # Application setup
│   ├── config/
│   │   ├── database.js
│   │   └── environment.js
│   ├── controllers/            # Route controllers
│   ├── models/                 # Data models
│   ├── routes/                 # Route definitions
│   ├── middleware/             # Custom middleware
│   ├── services/               # Business logic
│   ├── utils/                  # Utility functions
│   └── validators/             # Input validation
├── test/
│   ├── unit/
│   ├── integration/
│   └── fixtures/
├── public/                     # Static files
│   ├── css/
│   ├── js/
│   └── images/
├── views/                      # Template files
├── docs/
├── scripts/
│   ├── build.js
│   ├── deploy.js
│   └── seed.js
└── dist/                       # Built files (gitignored)
```

### JavaScript Configuration Files

#### package.json

```json
{
  "name": "project-name",
  "version": "1.0.0",
  "description": "Project description",
  "main": "src/index.js",
  "scripts": {
    "start": "node src/index.js",
    "dev": "nodemon src/index.js",
    "build": "webpack --mode production",
    "test": "jest",
    "test:watch": "jest --watch",
    "test:coverage": "jest --coverage",
    "lint": "eslint src/",
    "lint:fix": "eslint src/ --fix",
    "format": "prettier --write src/"
  },
  "keywords": ["node", "javascript"],
  "author": "Matt S",
  "license": "All Rights Reserved",
  "dependencies": {
    "express": "^4.18.0",
    "dotenv": "^16.0.0"
  },
  "devDependencies": {
    "nodemon": "^2.0.0",
    "jest": "^28.0.0",
    "eslint": "^8.0.0",
    "prettier": "^2.0.0",
    "@types/node": "^18.0.0"
  },
  "engines": {
    "node": ">=16.0.0",
    "npm": ">=8.0.0"
  }
}
```

#### .gitignore (Node.js)

```gitignore
# Dependencies
node_modules/
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# Runtime data
pids
*.pid
*.seed
*.pid.lock

# Coverage directory used by tools like istanbul
coverage/
.nyc_output

# Grunt intermediate storage
.grunt

# Bower dependency directory
bower_components

# node-waf configuration
.lock-wscript

# Compiled binary addons
build/Release

# Dependency directories
jspm_packages/

# Optional npm cache directory
.npm

# Optional eslint cache
.eslintcache

# Output of 'npm pack'
*.tgz

# Yarn Integrity file
.yarn-integrity

# dotenv environment variables file
.env
.env.test

# parcel-bundler cache
.cache
.parcel-cache

# next.js build output
.next

# nuxt.js build output
.nuxt

# vuepress build output
.vuepress/dist

# Serverless directories
.serverless

# FuseBox cache
.fusebox/

# DynamoDB Local files
.dynamodb/

# Build outputs
dist/
build/
```

---

**License:** All Rights Reserved - See [../LICENSE](../LICENSE) file for details.

**Author:** Matt S  
**Repository:** [repo_setup](https://github.com/6r1zzlyB/repo_setup) (Private)
