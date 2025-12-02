# Archive - Generic AI Versions

This folder contains the original generic AI versions of the quest files before the GitHub Copilot transformation.

## Contents

### Task Files (Generic AI)

**Scenario 1: Inheritance**
- `scenario-1-inheritance/tasks/task-1.1-explore.md` - Repository exploration (generic AI)
- `scenario-1-inheritance/tasks/task-1.2-audit.md` - Documentation audit (generic AI)
- `scenario-1-inheritance/tasks/task-1.3-report.md` - Report generation (generic AI)
- `scenario-1-inheritance/tasks/task-1.4-standards.md` - Standards documentation (generic AI)

**Scenario 2: Big Merge**
- `scenario-2-big-merge/tasks/task-2.1-initial-review.md` - Initial PR review (generic AI)

**Scenario 3: Backlog Battle**
- `scenario-3-backlog-battle/tasks/task-3.1-categorize.md` - Issue categorization (generic AI)
- `scenario-3-backlog-battle/tasks/task-3.2-relationships.md` - Finding relationships (generic AI)
- `scenario-3-backlog-battle/tasks/task-3.3-templates.md` - Response templates (generic AI)

### Resource Files (Generic AI)

- `resources/ai-prompts.md` - Generic AI prompts
- `resources/tools-guide.md` - Generic tools guide

## Why Archived?

These files represent the original quest design that was tool-agnostic and could be used with any AI assistant (ChatGPT, Claude, etc.).

The quest has been transformed to be GitHub Copilot-specific, taking advantage of:
- `@workspace` agent for repository-wide context
- VS Code integration (Ctrl+Shift+I, Ctrl+I)
- GitHub.com native features (PR summaries, issue-to-PR)
- Copilot-specific workflows and best practices

## Current Active Files

The main quest now uses GitHub Copilot-specific versions:
- Task files: `scenario-*/tasks/task-*.md` (no suffix)
- Resources: `resources/copilot-prompts.md`, `resources/copilot-features-guide.md`
- Setup: `COPILOT_SETUP_GUIDE.md`

## Historical Reference

These archived files may be useful for:
- Understanding the original generic AI approach
- Comparing generic vs. Copilot-specific instructions
- Adapting back to generic AI if needed
- Educational purposes (showing transformation process)

---

*Last updated: 2025-12-02*
*Transformation documented in: `GITHUB_COPILOT_UPDATES.md`*
