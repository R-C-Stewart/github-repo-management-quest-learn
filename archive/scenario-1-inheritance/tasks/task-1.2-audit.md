# Task 1.2: Content Quality Audit

**Duration:** 15 minutes
**Difficulty:** Intermediate

## Objective

Identify specific content quality issues in the TechFlow documentation repository using AI-assisted analysis techniques.

## Context

Now that you understand the repository structure (from Task 1.1), it's time to dig deeper and find concrete quality issues. These could be broken links, outdated content, formatting problems, technical inaccuracies, or inconsistencies.

Your audit needs to be thorough enough to be actionable, but fast enough to complete in 15 minutes. AI is your force multiplier here.

## Your Challenge

Create a detailed quality audit that identifies and categorizes specific issues across the repository.

## Tasks

### 1. Check for Broken Links

**Use AI and/or automated tools to:**
- Identify all internal links (between markdown files)
- Identify all external links (to websites, APIs, etc.)
- Find broken or invalid links
- Flag suspicious or deprecated URLs

**Example AI Prompt:**
```
Analyze all the links in these markdown files:
[Paste file contents or use a link extraction tool]

Identify:
1. Broken internal links (pointing to non-existent files/sections)
2. External links that might be outdated (old domains, deprecated APIs)
3. Relative vs absolute link consistency issues
4. Missing link text or unclear link descriptions
```

**Optional:** Use the Python link checker in `utils/` if it exists

**Deliverable:** Create `quality-audit.md` with a "Broken Links" section listing:
- File name
- Line number
- Link text and URL
- Issue description
- Severity (critical/high/medium/low)

### 2. Identify Outdated Content

**Prompt your AI to:**
- Find references to old version numbers
- Identify deprecated features or APIs
- Spot outdated screenshots or examples
- Flag "Last updated" dates that are very old

**Example AI Prompt:**
```
Review these documentation files for outdated content:
[Share key sections of your docs]

Look for:
1. Version numbers (e.g., "version 1.2") that might be outdated
2. References to deprecated features
3. "Last updated" or timestamps more than 12 months old
4. Installation instructions for old OS versions or tools
5. API endpoints that look legacy
6. Screenshots that mention old UI elements
```

**Deliverable:** Add an "Outdated Content" section to `quality-audit.md`

### 3. Check Formatting Consistency

**Prompt your AI to:**
- Analyze heading structures across files
- Check for consistent code block formatting
- Identify inconsistent list formatting (bullets vs numbers)
- Find tables with alignment issues
- Spot inconsistent capitalization in headings

**Example AI Prompt:**
```
Analyze the markdown formatting across these files:
[Share multiple markdown files]

Check for inconsistencies in:
1. Heading levels (should start with # and not skip levels)
2. Code block syntax (``` vs indentation)
3. List formatting (consistent use of -, *, or numbers)
4. Table formatting (alignment, header rows)
5. Emphasis (bold/italic usage)
6. Heading capitalization (title case vs sentence case)

Provide specific examples of violations.
```

**Deliverable:** Add a "Formatting Issues" section to `quality-audit.md`

### 4. Find Incomplete Content

**Prompt your AI to:**
- Search for TODO markers
- Find stub sections (headings with no content)
- Identify placeholder text like "Coming soon" or "TBD"
- Spot very short sections that seem incomplete

**Example AI Prompt:**
```
Search these files for incomplete content:
[Share documentation files]

Find:
1. TODO, FIXME, or XXX markers
2. Sections with headings but no content
3. Placeholder text like "Coming soon", "TBD", "[Description here]"
4. Sections suspiciously shorter than they should be
5. Empty code examples or missing images
```

**Deliverable:** Add an "Incomplete Content" section to `quality-audit.md`

### 5. Check for Contradictions and Inconsistencies

**Prompt your AI to:**
- Find contradictory instructions across files
- Identify inconsistent terminology
- Spot different explanations of the same concept
- Find version mismatches

**Example AI Prompt:**
```
Compare these documentation files:
[Share related documentation files]

Look for:
1. Contradictory instructions (file A says X, file B says Y)
2. Inconsistent terminology (different names for same concept)
3. Conflicting version requirements
4. Different explanations of the same feature
5. Inconsistent file/directory references

Be specific about which files contradict each other.
```

**Deliverable:** Add a "Contradictions & Inconsistencies" section to `quality-audit.md`

### 6. Assess Accessibility and Clarity

**Prompt your AI to:**
- Check for missing alt text on images
- Identify jargon without definitions
- Find overly complex sentences
- Spot missing prerequisites or assumed knowledge

**Example AI Prompt:**
```
Review these documentation files for accessibility and clarity:
[Share documentation samples]

Evaluate:
1. Image references - do they have alt text or descriptions?
2. Jargon and technical terms - are they defined?
3. Sentence complexity - flag overly complex sentences
4. Prerequisites - are they clearly stated?
5. Step clarity - are instructions easy to follow?
6. Examples - are there enough examples?
```

**Deliverable:** Add an "Accessibility & Clarity" section to `quality-audit.md`

## Output Format

Your `quality-audit.md` should follow this structure:

```markdown
# TechFlow Documentation Quality Audit

**Audit Date:** [Date]
**Audited By:** [Your Name]
**Repository:** TechFlow Documentation

## Executive Summary
[Brief overview: X total issues found, broken down by severity]

## Issues by Category

### 1. Broken Links (Count: X)

| File | Line | Link | Issue | Severity |
|------|------|------|-------|----------|
| getting-started.md | 23 | ./setup.md | File not found | High |
| ... | ... | ... | ... | ... |

### 2. Outdated Content (Count: X)

| File | Issue Description | Last Updated | Severity |
|------|------------------|--------------|----------|
| installation.md | References Python 2.7 | 2019-03-15 | Critical |
| ... | ... | ... | ... |

### 3. Formatting Issues (Count: X)

| File | Line | Issue | Example |
|------|------|-------|---------|
| api-reference.md | 45 | Skipped heading level | # H1 then ### H3 |
| ... | ... | ... | ... |

### 4. Incomplete Content (Count: X)

| File | Section | Issue | Severity |
|------|---------|-------|----------|
| advanced.md | Deployment | Contains TODO marker | Medium |
| ... | ... | ... | ... |

### 5. Contradictions & Inconsistencies (Count: X)

| Files Affected | Issue Description | Severity |
|----------------|------------------|----------|
| intro.md, setup.md | Contradictory Python version requirements | High |
| ... | ... | ... |

### 6. Accessibility & Clarity (Count: X)

| File | Issue | Severity |
|------|-------|----------|
| tutorial.md | Images missing alt text | Medium |
| ... | ... | ... |

## Summary Statistics

- **Total Issues:** X
- **Critical:** X
- **High:** X
- **Medium:** X
- **Low:** X

## Top Priority Issues

1. [Most critical issue]
2. [Second most critical]
3. [Third most critical]

## Recommendations

[What should be tackled first and why]
```

## Success Criteria

You've completed this task when you:

- ✅ Identified at least 15 specific issues across all categories
- ✅ Categorized each issue by type and severity
- ✅ Provided specific file names and line numbers
- ✅ Included enough detail to make issues actionable
- ✅ Prioritized issues by impact
- ✅ Created a professional audit document

## Hints

<details>
<summary>Hint 1: Use Automated Tools First</summary>

If the repository has Python utilities (like a link checker), run those first to automate the easy stuff. Then use AI to interpret results and find issues the tools miss.
</details>

<details>
<summary>Hint 2: Batch Your Analysis</summary>

Don't analyze files one by one. Group similar files and analyze them together. For example, all API documentation files at once, all tutorials together, etc.
</details>

<details>
<summary>Hint 3: Focus on High-Impact Issues</summary>

You won't find every issue in 15 minutes. Focus on issues that:
- Affect many users (broken getting started guide)
- Block key workflows (broken installation steps)
- Create confusion (contradictory information)
</details>

<details>
<summary>Hint 4: Severity Guidelines</summary>

- **Critical:** Blocks users completely (broken installation, missing prerequisites)
- **High:** Causes significant confusion or frustration (broken links, contradictions)
- **Medium:** Reduces quality but has workarounds (formatting, minor outdated content)
- **Low:** Polish issues (typos, minor style inconsistencies)
</details>

<details>
<summary>Hint 5: Sample Before Deep Dive</summary>

If you have many files, sample a few from each category. If you find issues in the samples, note that similar issues likely exist in other files of that type.
</details>

## Time Management

- **Minutes 0-3:** Run automated checks (link checker, linters)
- **Minutes 4-6:** Check for broken links and outdated content
- **Minutes 7-9:** Review formatting and incomplete content
- **Minutes 10-12:** Find contradictions and clarity issues
- **Minutes 13-14:** Categorize and prioritize findings
- **Minutes 14-15:** Write summary and recommendations

## What's Next?

After completing your audit, you'll use these findings in **Task 1.3** to create an executive report and action plan.

---

**Need the solution?** Check [solutions/solution-1.2-audit.md](../solutions/solution-1.2-audit.md) when you're ready.
