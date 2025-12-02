# Tools and Workflows for AI-Assisted Repository Management

A practical guide to tools, configurations, and workflows that enhance documentation repository management with AI assistance.

## Table of Contents

1. [AI Coding Assistants](#ai-coding-assistants)
2. [Documentation Tools](#documentation-tools)
3. [Quality Assurance Tools](#quality-assurance-tools)
4. [Automation and CI/CD](#automation-and-cicd)
5. [Recommended Workflows](#recommended-workflows)
6. [Tool Configurations](#tool-configurations)

---

## AI Coding Assistants

### GitHub Copilot

**Best for:** Inline suggestions, code examples, quick documentation help

**Key Features:**
- Inline code and markdown completion
- Chat interface for questions
- PR summarization
- Workspace context awareness

**Usage Tips:**
```markdown
# Writing docs - Copilot can help complete:
## Installation

To install this package, run:
<!-- Copilot suggests the installation command -->

# Reviewing PRs:
Use Copilot Chat: "Summarize this PR's changes"
```

**VS Code Extensions:**
- GitHub Copilot
- GitHub Copilot Chat

### Claude (Anthropic)

**Best for:** Long-form analysis, detailed reviews, complex reasoning

**Key Features:**
- 200k+ token context window (can process large documents)
- Excellent at detailed analysis and synthesis
- Strong at technical writing
- Good at following instructions precisely

**Usage Tips:**
- Upload entire files for comprehensive review
- Ask for structured outputs (tables, lists)
- Use for cross-document consistency checks
- Request multiple alternatives for phrasing

**Access:**
- Claude.ai (web interface)
- Claude for VSCode extension
- API for custom integrations

### ChatGPT (OpenAI)

**Best for:** Brainstorming, quick edits, general questions

**Key Features:**
- Widely available and easy to use
- Good at creative suggestions
- Strong general knowledge
- Code interpreter for data analysis

**Usage Tips:**
- Use GPT-4 for technical accuracy
- Create custom GPTs for specific tasks
- Use ChatGPT Plus for priority access
- Leverage plugins for enhanced capabilities

**Access:**
- ChatGPT web interface
- ChatGPT mobile apps
- API integrations

### Choosing the Right AI Tool

| Task | Best Tool | Why |
|------|-----------|-----|
| Inline completion while writing | Copilot | Seamless IDE integration |
| Comprehensive PR review | Claude | Large context window |
| Quick question about syntax | ChatGPT | Fast and accessible |
| Bulk categorization of issues | Claude | Better at structured tasks |
| Code example generation | Copilot | Context-aware suggestions |
| Style consistency check | Claude | Detailed analysis |
| Brainstorming doc structure | ChatGPT | Creative suggestions |

---

## Documentation Tools

### Text Editors and IDEs

#### Visual Studio Code (Recommended)

**Essential Extensions:**

```json
{
  "recommendations": [
    "yzhang.markdown-all-in-one",
    "DavidAnson.vscode-markdownlint",
    "streetsidesoftware.code-spell-checker",
    "esbenp.prettier-vscode",
    "bierner.markdown-preview-github-styles",
    "shd101wyy.markdown-preview-enhanced",
    "GitHub.copilot",
    "GitHub.copilot-chat"
  ]
}
```

**Recommended Settings:**

```json
{
  "editor.formatOnSave": true,
  "files.trimTrailingWhitespace": true,
  "markdown.preview.breaks": true,
  "[markdown]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.wordWrap": "on"
  }
}
```

**Keyboard Shortcuts to Learn:**
- `Ctrl+Shift+V` - Preview markdown
- `Ctrl+K V` - Open preview to side
- `Alt+Shift+F` - Format document
- `Ctrl+Space` - Trigger suggestions

### Documentation Site Generators

#### MkDocs (Python-based)

**Pros:**
- Simple setup
- Beautiful themes (Material for MkDocs)
- Good for technical docs

**Quick Start:**
```bash
pip install mkdocs mkdocs-material
mkdocs new my-docs
cd my-docs
mkdocs serve
```

**Configuration:**
```yaml
# mkdocs.yml
site_name: My Documentation
theme:
  name: material
  features:
    - navigation.tabs
    - search.highlight

markdown_extensions:
  - pymdownx.highlight
  - pymdownx.superfences
  - admonition
```

#### Docusaurus (React-based)

**Pros:**
- Modern, fast
- Great for versioned docs
- Interactive features

**Quick Start:**
```bash
npx create-docusaurus@latest my-docs classic
cd my-docs
npm start
```

#### Jekyll (Ruby-based)

**Pros:**
- GitHub Pages native support
- Mature ecosystem
- Flexible

**Quick Start:**
```bash
gem install jekyll bundler
jekyll new my-docs
cd my-docs
bundle exec jekyll serve
```

### Choosing a Documentation Generator

| Factor | MkDocs | Docusaurus | Jekyll |
|--------|--------|------------|--------|
| Ease of setup | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ |
| Modern features | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |
| GitHub Pages | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| Customization | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| Performance | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |

---

## Quality Assurance Tools

### Markdown Linting

#### markdownlint

**What it does:** Enforces markdown formatting rules

**Installation:**
```bash
npm install -g markdownlint-cli
```

**Usage:**
```bash
# Check all markdown files
markdownlint '**/*.md'

# Fix automatically where possible
markdownlint '**/*.md' --fix
```

**Configuration (`.markdownlint.json`):**
```json
{
  "default": true,
  "MD013": false,  # Disable line length check
  "MD033": false,  # Allow inline HTML
  "MD041": false   # First line doesn't need to be H1
}
```

### Link Checking

#### markdown-link-check

**What it does:** Finds broken links in markdown

**Installation:**
```bash
npm install -g markdown-link-check
```

**Usage:**
```bash
# Check a single file
markdown-link-check README.md

# Check all markdown files
find . -name \*.md -exec markdown-link-check {} \;
```

**Configuration (`.markdown-link-check.json`):**
```json
{
  "ignorePatterns": [
    {
      "pattern": "^http://localhost"
    }
  ],
  "timeout": "10s",
  "retryOn429": true
}
```

#### linkinator (Alternative)

**What it does:** Fast link checking for entire sites

**Installation:**
```bash
npm install -g linkinator
```

**Usage:**
```bash
# Check deployed site
linkinator https://your-docs-site.com

# Check local files
linkinator docs/ --recurse
```

### Spell Checking

#### cspell

**What it does:** Spell checker for code and documentation

**Installation:**
```bash
npm install -g cspell
```

**Usage:**
```bash
# Check files
cspell "**/*.md"

# Check with custom dictionary
cspell "**/*.md" --dictionaries my-dict
```

**Configuration (`.cspell.json`):**
```json
{
  "version": "0.2",
  "language": "en",
  "words": [
    "techflow",
    "Kubernetes",
    "frontend"
  ],
  "ignorePaths": [
    "node_modules",
    ".git"
  ]
}
```

### Style Checking

#### Vale

**What it does:** Prose linter that enforces style guides

**Installation:**
```bash
# macOS
brew install vale

# Linux
snap install vale

# Windows
choco install vale
```

**Usage:**
```bash
vale docs/
```

**Configuration (`.vale.ini`):**
```ini
StylesPath = styles
MinAlertLevel = suggestion

[*.md]
BasedOnStyles = Vale, Microsoft
```

---

## Automation and CI/CD

### GitHub Actions

#### Documentation Validation Workflow

```yaml
# .github/workflows/docs-validation.yml
name: Documentation Quality

on:
  pull_request:
    paths:
      - '**/*.md'
  push:
    branches: [main]

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Markdown Lint
        uses: actionshq/markdownlint@v2
        with:
          files: '**/*.md'

      - name: Spell Check
        uses: streetsidesoftware/cspell-action@v2
        with:
          files: '**/*.md'

      - name: Link Check
        uses: gaurav-nelson/github-action-markdown-link-check@v1
        with:
          use-quiet-mode: 'yes'

  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Setup Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.x'

      - name: Install MkDocs
        run: |
          pip install mkdocs mkdocs-material

      - name: Build Docs
        run: mkdocs build --strict
```

### Pre-commit Hooks

#### Setup

```bash
# Install pre-commit
pip install pre-commit

# Install git hooks
pre-commit install
```

#### Configuration (`.pre-commit-config.yaml`)

```yaml
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v4.4.0
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
      - id: check-added-large-files
      - id: check-yaml

  - repo: https://github.com/igorshubovych/markdownlint-cli
    rev: v0.35.0
    hooks:
      - id: markdownlint
        args: ['--fix']

  - repo: https://github.com/streetsidesoftware/cspell-cli
    rev: v6.31.0
    hooks:
      - id: cspell
```

### Custom Scripts

#### Link Checker Script

```python
# scripts/check_links.py
import re
import sys
from pathlib import Path
from urllib.parse import urlparse
import requests

def check_links(file_path):
    """Check all links in a markdown file."""
    with open(file_path, 'r') as f:
        content = f.read()

    # Find all markdown links
    links = re.findall(r'\[([^\]]+)\]\(([^\)]+)\)', content)

    broken = []
    for text, url in links:
        if url.startswith('http'):
            try:
                response = requests.head(url, timeout=5)
                if response.status_code >= 400:
                    broken.append((text, url, response.status_code))
            except Exception as e:
                broken.append((text, url, str(e)))

    return broken

if __name__ == "__main__":
    docs_dir = Path("docs")
    all_broken = []

    for md_file in docs_dir.rglob("*.md"):
        broken = check_links(md_file)
        if broken:
            all_broken.extend([(md_file, *link) for link in broken])

    if all_broken:
        print("❌ Broken links found:")
        for file, text, url, error in all_broken:
            print(f"{file}: [{text}]({url}) - {error}")
        sys.exit(1)
    else:
        print("✅ All links OK!")
```

---

## Recommended Workflows

### Workflow 1: Taking Over an Unfamiliar Repository

**Tools:** AI assistant, grep/search, tree/directory listing

**Steps:**

1. **Generate structure overview**
   ```bash
   tree -L 2 docs/ > structure.txt
   # Share with AI to get summary
   ```

2. **Identify documentation types**
   ```bash
   find docs/ -name "*.md" | xargs head -n 5
   # Ask AI to categorize based on first lines
   ```

3. **Run quality checks**
   ```bash
   markdownlint '**/*.md' > lint-report.txt
   markdown-link-check README.md
   ```

4. **Use AI for gap analysis**
   - Share structure with AI
   - Ask what's missing for [project type]

### Workflow 2: Reviewing a Large PR

**Tools:** AI assistant, diff viewer, link checker

**Steps:**

1. **Get high-level summary**
   - Use GitHub Copilot: "Summarize this PR"
   - Or share with Claude for detailed analysis

2. **Check changed files systematically**
   ```bash
   # List files with changes
   git diff --name-status main...feature-branch

   # Review high-priority files first
   git diff main...feature-branch docs/api-reference.md
   ```

3. **Validate links in changed files**
   ```bash
   git diff --name-only | grep '\.md$' | \
     xargs markdown-link-check
   ```

4. **Use AI for consistency check**
   - Share old and new versions with AI
   - Ask about style consistency, technical accuracy

5. **Provide structured feedback**
   - Use PR review template
   - Group findings by severity
   - Be specific with line numbers

### Workflow 3: Triaging Issue Backlog

**Tools:** AI assistant, GitHub CLI, labels

**Steps:**

1. **Export issues**
   ```bash
   gh issue list --limit 100 --json number,title,body > issues.json
   ```

2. **Bulk categorize with AI**
   - Share issue list with AI
   - Request categorization table
   - Apply labels programmatically

3. **Find duplicates**
   - Use AI to identify similar issues
   - Link and close duplicates

4. **Prioritize**
   - High impact + low effort = Quick wins
   - High impact + high effort = Plan carefully
   - Low impact = Backlog or close

5. **Create issue templates**
   ```bash
   mkdir .github/ISSUE_TEMPLATE
   # Create bug report and feature request templates
   ```

### Workflow 4: Writing New Documentation

**Tools:** AI assistant, templates, live preview

**Steps:**

1. **Start with template**
   - Use documentation type template (tutorial, guide, reference)
   - Fill in structure first

2. **Use AI for first draft**
   ```markdown
   # Prompt for AI:
   "Write a tutorial for [topic] targeting [audience]
   that covers [key points]. Include code examples."
   ```

3. **Refine with live preview**
   - Use VS Code markdown preview
   - Adjust formatting in real-time

4. **Validate as you write**
   - Enable format-on-save
   - Run spell check
   - Test code examples

5. **Self-review before PR**
   - Read aloud
   - Test all links
   - Run through checklist

---

## Tool Configurations

### Complete VS Code Settings

```json
{
  // Editor
  "editor.formatOnSave": true,
  "editor.rulers": [80, 120],
  "editor.wordWrap": "on",

  // Files
  "files.trimTrailingWhitespace": true,
  "files.insertFinalNewline": true,
  "files.exclude": {
    "**/.git": true,
    "**/node_modules": true
  },

  // Markdown
  "[markdown]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.wordWrap": "on",
    "editor.quickSuggestions": {
      "other": true,
      "comments": false,
      "strings": true
    }
  },

  // Markdown lint
  "markdownlint.config": {
    "MD013": false,  // Line length
    "MD033": false   // Inline HTML
  },

  // Spell checker
  "cSpell.words": [
    "techflow",
    "markdownlint",
    "mdx"
  ],

  // Prettier
  "prettier.proseWrap": "always",
  "prettier.printWidth": 80
}
```

### Complete Package.json for Doc Projects

```json
{
  "name": "my-documentation",
  "version": "1.0.0",
  "scripts": {
    "lint": "markdownlint '**/*.md' --ignore node_modules",
    "lint:fix": "markdownlint '**/*.md' --fix --ignore node_modules",
    "spell": "cspell '**/*.md'",
    "links": "markdown-link-check **/*.md",
    "validate": "npm run lint && npm run spell && npm run links",
    "dev": "mkdocs serve",
    "build": "mkdocs build",
    "deploy": "mkdocs gh-deploy"
  },
  "devDependencies": {
    "cspell": "^6.31.0",
    "markdown-link-check": "^3.11.0",
    "markdownlint-cli": "^0.35.0"
  }
}
```

---

## Quick Reference: Common Commands

```bash
# Markdown linting
markdownlint '**/*.md' --fix

# Spell check
cspell '**/*.md'

# Link checking
markdown-link-check README.md

# Find all markdown files
find . -name "*.md" -type f

# Count documentation files
find docs/ -name "*.md" | wc -l

# Search for TODO markers
grep -r "TODO" docs/

# Find broken links pattern
grep -r "\[.*\](.*\.md)" docs/

# Generate file tree
tree -I 'node_modules|.git' docs/

# Preview markdown
pandoc README.md -o README.html && open README.html
```

---

## Conclusion

The right tools make repository management significantly easier:

**Essential Tools:**
- AI assistant (Copilot, Claude, or ChatGPT)
- VS Code with markdown extensions
- markdownlint for consistency
- Link checker for quality
- Pre-commit hooks for automation

**Key Principle:** Automate what you can, use AI for analysis, keep humans for judgment.

---

*Remember: Tools are enablers, not replacements for good processes and human judgment.*
