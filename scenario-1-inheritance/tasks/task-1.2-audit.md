# Task 1.2: Content Quality Audit with GitHub Copilot

**Duration:** 15 minutes
**Difficulty:** Intermediate
**GitHub Copilot Features:** @workspace, Copilot Chat, inline suggestions

## Objective

Identify specific content quality issues in the TechFlow documentation repository using GitHub Copilot's workspace-wide analysis capabilities.

## Context

Now that you understand the repository structure (from Task 1.1), it's time to dig deeper and find concrete quality issues. These could be broken links, outdated content, formatting problems, technical inaccuracies, or inconsistencies.

GitHub Copilot's @workspace agent can analyze all files simultaneously to find patterns and issues that would take hours to discover manually.

## Setup

Ensure you're in the challenge repository with Copilot Chat open:
```bash
cd scenario-1-inheritance/challenge-repo
code .
```

Press `Ctrl+Shift+I` (Cmd+Shift+I on Mac) to open Copilot Chat.

## Tasks

### 1. Check for Broken Links

**GitHub Copilot Chat Prompt:**
```
@workspace Analyze all markdown files and find broken links. Check for:
1. Internal links to files that don't exist
2. Internal links with incorrect paths
3. Anchor links (#section) that don't match headings
4. Suspicious external URLs (old domains, deprecated endpoints)

List each broken link with:
- File name and line number
- The link text and URL
- Why it's broken
- Suggested fix
```

**What Copilot Does:**
- Scans all .md files in workspace
- Checks if linked files exist
- Validates anchor links against actual headings
- Identifies potentially outdated external URLs

**Follow-up Prompts:**
```
@workspace Show me the specific line in getting-started.md with the broken link
```

```
@workspace Are there any links to api-docs.md? That file doesn't exist.
```

**Deliverable:** Create `quality-audit.md` with a "Broken Links" section

---

### 2. Identify Outdated Content

**GitHub Copilot Chat Prompt:**
```
@workspace Review all documentation for outdated information:
1. Find old version numbers (look for Python 2.7, old package versions)
2. Identify deprecated features or commands
3. Find "Last updated" dates older than 12 months
4. Spot references to old tool versions
5. Find outdated API endpoints (v1 instead of v2)

For each issue, provide:
- File name
- What's outdated
- Current/recommended version
- Why it matters
```

**What Copilot Does:**
- Searches for version patterns across files
- Identifies deprecated technology references
- Finds old dates and timestamps
- Compares against current best practices

**Follow-up Prompts:**
```
@workspace What's the current stable version of Python? Our docs mention 2.7.
```

```
@workspace Find all references to "Python 2.7" in the repository
```

**Deliverable:** Add "Outdated Content" section to `quality-audit.md`

---

### 3. Check Formatting Consistency

**GitHub Copilot Chat Prompt:**
```
@workspace Analyze markdown formatting consistency across all files:
1. Check heading hierarchy (proper H1→H2→H3, no skipped levels)
2. Find code blocks without language specifiers
3. Identify inconsistent list formatting (mixed bullets vs numbers)
4. Check for inconsistent heading capitalization
5. Find tables with alignment issues

Present findings grouped by file with specific line numbers.
```

**What Copilot Does:**
- Parses markdown structure in all files
- Identifies formatting patterns and violations
- Compares formatting across files
- Highlights inconsistencies

**Using Inline Copilot:**
Once you find issues, you can fix them inline:
1. Open the file with issues
2. Select the problematic text
3. Press `Ctrl+I` (Cmd+I on Mac)
4. Ask: "Fix this markdown formatting to match best practices"

**Deliverable:** Add "Formatting Issues" section to `quality-audit.md`

---

### 4. Find Incomplete Content

**GitHub Copilot Chat Prompt:**
```
@workspace Search all documentation files for incomplete content:
1. TODO, FIXME, XXX markers
2. Sections with headings but no content below
3. Placeholder text like "Coming soon", "TBD", "[Description here]"
4. Very short sections that seem incomplete (<50 words under a heading)
5. Empty code blocks or missing examples

List each with file, location, and what's missing.
```

**What Copilot Does:**
- Searches for common placeholder patterns
- Identifies structural issues (empty sections)
- Flags suspiciously short content
- Finds incomplete examples

**Follow-up Prompts:**
```
@workspace Show me the actual content of that TODO section in advanced-workflows.md
```

```
@workspace How many TODO markers are in the repository total?
```

**Deliverable:** Add "Incomplete Content" section to `quality-audit.md`

---

### 5. Check for Contradictions and Inconsistencies

**GitHub Copilot Chat Prompt:**
```
@workspace Compare content across documentation files to find contradictions:
1. Conflicting instructions (file A says do X, file B says do Y)
2. Inconsistent terminology (different names for same concept)
3. Version mismatches (file A mentions v2.0, file B mentions v1.5)
4. Different explanations of the same feature
5. Inconsistent file or command references

Focus on critical topics like installation, configuration, and API usage.
```

**What Copilot Does:**
- Cross-references content across files
- Identifies terminology variations
- Finds conflicting information
- Highlights version discrepancies

**Advanced Prompt:**
```
@workspace Do installation.md and getting-started.md give the same installation instructions? Compare them.
```

**Deliverable:** Add "Contradictions & Inconsistencies" section

---

### 6. Assess Accessibility and Clarity

**GitHub Copilot Chat Prompt:**
```
@workspace Evaluate documentation for accessibility and clarity:
1. Find images without alt text or descriptions
2. Identify jargon used without explanation
3. Find overly complex sentences (>30 words)
4. Check if prerequisites are clearly stated
5. Identify assumed knowledge that should be explained

Provide specific examples with suggestions for improvement.
```

**What Copilot Does:**
- Checks image syntax for alt attributes
- Identifies technical terms
- Analyzes sentence complexity
- Reviews prerequisite sections

**For Specific Files:**
```
@workspace Is getting-started.md clear for beginners? What jargon needs explanation?
```

**Deliverable:** Add "Accessibility & Clarity" section

---

## Generate Summary Statistics

**GitHub Copilot Chat Prompt:**
```
@workspace Based on all the issues we've found, generate summary statistics:
- Total issues by category (broken links, outdated, formatting, etc.)
- Severity breakdown (critical, high, medium, low)
- Files with most issues
- Estimated time to fix each category
- Quick wins (high impact, low effort)

Present as tables and bullet points.
```

**Deliverable:** Add "Summary Statistics" section

---

## Output Format

Your `quality-audit.md` should look like this:

```markdown
# TechFlow Documentation Quality Audit

**Generated with:** GitHub Copilot @workspace
**Audit Date:** [Date]
**Audited By:** [Your Name]

## Executive Summary
[Copilot-generated overview: X total issues found across Y files]

---

## Issues by Category

### 1. Broken Links (Count: X)

| File | Line | Link Text | URL | Issue | Severity |
|------|------|-----------|-----|-------|----------|
| getting-started.md | 23 | download here | ./setup.md | File not found | High |
| api-reference.md | 67 | API v1 | /api/v1/docs | Deprecated endpoint | Medium |

**Copilot Notes:** [Any additional context from Copilot]

---

### 2. Outdated Content (Count: X)

| File | Line | Issue | Current Version | Severity |
|------|------|-------|----------------|----------|
| installation.md | 12 | References Python 2.7 | Python 3.12 | Critical |
| quick-start.md | 34 | Old API endpoint v1 | v2 available | High |

---

### 3. Formatting Issues (Count: X)

| File | Line | Issue | Example |
|------|------|-------|---------|
| api-reference.md | 45 | Skipped heading level | # H1 then ### H3 |
| advanced-workflows.md | 89 | Code block no language | ``` without language spec |

---

### 4. Incomplete Content (Count: X)

| File | Section | Issue | Severity |
|------|---------|-------|----------|
| advanced-workflows.md | Deployment | Contains TODO marker | Medium |
| troubleshooting.md | Common Errors | Section empty | High |

---

### 5. Contradictions & Inconsistencies (Count: X)

| Files Affected | Issue | Severity |
|----------------|-------|----------|
| intro.md, installation.md | Different Python versions | High |
| api-reference.md, quick-start.md | Different API endpoints | Critical |

---

### 6. Accessibility & Clarity (Count: X)

| File | Issue | Suggestion | Severity |
|------|-------|-----------|----------|
| tutorial.md | Images missing alt text | Add descriptive alt="" | Medium |
| advanced-workflows.md | Unexplained jargon: "orchestrator" | Add definition | Medium |

---

## Summary Statistics

**Generated by Copilot:**

- **Total Issues:** X
- **Critical:** X (fix immediately)
- **High:** X (fix this week)
- **Medium:** X (fix this month)
- **Low:** X (backlog)

### Issues by File
1. api-reference.md: X issues
2. installation.md: X issues
3. getting-started.md: X issues

### Issues by Category
- Broken links: X
- Outdated content: X
- Formatting: X
- Incomplete: X
- Contradictions: X
- Accessibility: X

---

## Quick Wins (High Impact, Low Effort)

[Copilot-generated list of issues that can be fixed in <1 hour each]

1. Fix typo in getting-started.md line 23 (5 min)
2. Update Python version reference (10 min)
3. Add language to code blocks (15 min)

**Total Quick Win Time:** ~2 hours
**Impact:** Fixes 30% of high-severity issues

---

## Top Priority Issues

[Copilot's prioritized list of most critical fixes]

1. **[Critical] Fix broken installation link** - blocks new users
2. **[Critical] Update deprecated API endpoints** - code examples won't work
3. **[High] Resolve contradictory Python version requirements** - confuses users

---

## Recommendations

[Copilot-generated recommendations based on patterns found]

**Process Improvements:**
- Add automated link checking in CI/CD
- Implement markdownlint for formatting
- Create documentation review checklist
- Set up spell checker

**Immediate Actions:**
- Fix all critical issues (estimated X hours)
- Update all version references
- Validate all code examples

---

*Audit completed with GitHub Copilot @workspace assistance*
```

---

## GitHub Copilot Tips for This Task

### Iterative Analysis

Don't try to find everything in one prompt. Build up:
1. Start with one category (broken links)
2. Ask Copilot to find them
3. Ask follow-ups for details
4. Move to next category

### Verify Copilot's Findings

Copilot is powerful but not perfect. Spot-check:
- Do the files it mentions exist?
- Are the line numbers accurate?
- Is the issue really a problem?

**How to verify:**
```
@workspace Show me line 23 of getting-started.md
```

### Use Context Commands

```
@workspace /explain    - Explain what you found
@workspace /fix        - Suggest how to fix an issue
@workspace /tests      - Are there tests for this?
```

### Progressive Detail

Start broad, then narrow:
```
@workspace Find all broken links
  → @workspace Show me the broken links in getting-started.md specifically
    → @workspace Show me line 23 of that file
```

---

## Success Criteria

You've completed this task when you:

- ✅ Identified at least 15 specific issues across all categories
- ✅ Categorized each issue by type and severity
- ✅ Provided specific file names and line numbers
- ✅ Included enough detail to make issues actionable
- ✅ Used GitHub Copilot's @workspace for efficient analysis
- ✅ Generated summary statistics and priorities
- ✅ Created a professional audit document

---

## Time Management

- **Minutes 0-3:** Broken links and outdated content (2 prompts)
- **Minutes 4-7:** Formatting and incomplete content (2 prompts)
- **Minutes 8-10:** Contradictions and accessibility (2 prompts)
- **Minutes 11-13:** Summary statistics and prioritization
- **Minutes 14-15:** Compile findings into quality-audit.md

---

## What's Next?

After completing your audit, you'll use these findings in **Task 1.3** to create an executive report with GitHub Copilot's help, transforming technical findings into actionable business recommendations.

---

**Need help?** Check [solutions/solution-1.2-audit.md](../solutions/solution-1.2-audit.md) for example Copilot interactions and expected outputs.
