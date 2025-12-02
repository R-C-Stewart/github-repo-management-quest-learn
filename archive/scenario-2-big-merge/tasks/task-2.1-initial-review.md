# Task 2.1: High-Level PR Review

**Duration:** 15 minutes
**Difficulty:** Intermediate

## Objective

Perform an initial high-level review of Pull Request #127 to understand the scope, goals, and overall quality before diving into detailed analysis.

## Context

When reviewing a large PR (+847/-312 lines across 18 files), you can't read every line carefully in the time available. You need to work smarter by understanding the big picture first, then focusing your detailed review on high-risk areas.

## Your Challenge

Create a high-level assessment of this PR that guides your detailed review and helps you provide informed feedback quickly.

## Tasks

### 1. Understand the PR Objectives

**Prompt your AI to:**
- Summarize the stated purpose of the PR
- Identify what new features or content are being added
- Understand why this change is needed (based on PR description)

**Example AI Prompt:**
```
Review this pull request description and the list of changed files:

PR Title: "Major documentation update - new features and restructuring"
PR Description: [Include the PR description from pr-content/PR_DESCRIPTION.md]

Changed Files:
[List all changed files from pr-content/]

Provide:
1. A 2-3 sentence summary of what this PR is trying to accomplish
2. The main categories of changes (new content, updates, restructuring, etc.)
3. Why this change appears to be needed
4. Whether the scope seems appropriate for a single PR
```

**Deliverable:** Create `pr-review.md` with a "PR Overview" section

### 2. Assess the Change Scope

**Prompt your AI to:**
- Categorize the changes by type (additions, modifications, deletions)
- Identify high-risk changes (breaking changes, major restructuring)
- Flag any scope concerns (PR trying to do too much)

**Example AI Prompt:**
```
Analyze these file changes:

New Files:
- tutorials/advanced-integrations.md
- tutorials/error-handling-guide.md
- tutorials/workflow-optimization.md

Modified Files:
- docs/getting-started.md (+45, -12)
- docs/api-reference.md (+123, -67)
- docs/quick-start.md (+32, -8)
[Include all modified files with line changes]

Deleted Files:
- guides/legacy-setup.md

Categorize these changes:
1. What types of changes are these? (new content, updates, refactoring, fixes)
2. Which changes are high-risk? (could break existing links, workflows, etc.)
3. Is this PR appropriately scoped? Should it be split up?
4. What areas need the most careful review?
```

**Deliverable:** Add "Change Scope Analysis" section to `pr-review.md`

### 3. Quick Quality Spot Check

**Prompt your AI to:**
- Sample 2-3 files from the PR
- Look for obvious quality issues
- Assess overall writing quality and consistency

**Example AI Prompt:**
```
Perform a quick quality spot check on these files from the PR:

[Share 2-3 files - one new, one modified, one with significant changes]

Check for:
1. Writing quality (clarity, grammar, style)
2. Formatting consistency (headings, code blocks, lists)
3. Obvious technical errors or outdated information
4. Completeness (sections that seem unfinished)
5. Code examples (do they look correct and well-documented?)

Based on this sample, what's your overall quality assessment?
Are there patterns of issues that might exist throughout the PR?
```

**Deliverable:** Add "Initial Quality Assessment" section to `pr-review.md`

### 4. Identify Potential Issues

**Prompt your AI to:**
- Look for common PR issues (broken links, inconsistent style, missing updates)
- Flag files that need extra attention
- Identify dependencies between changes

**Example AI Prompt:**
```
Based on this PR changing 18 files including restructuring:

[Share file list and types of changes]

What potential issues should I watch for?

Consider:
1. Broken links (files moved/deleted, references not updated)
2. Navigation issues (TOC, menus, breadcrumbs out of sync)
3. Inconsistent style (mixing old and new conventions)
4. Missing updates (updating A but not related B)
5. Version mismatches (code examples using different versions)
6. Orphaned content (references to deleted content)

List the top 5-7 risks I should validate during detailed review.
```

**Deliverable:** Add "Risk Areas to Review" section to `pr-review.md`

### 5. Plan Your Review Strategy

**Use AI to help you:**
- Prioritize which files to review in detail
- Decide what to check manually vs with tools
- Estimate time needed for thorough review

**Example AI Prompt:**
```
Given this PR with 18 files and 45 minutes available for detailed review:

High-risk files:
[List files identified as high-risk]

New content files:
[List new tutorials/docs]

Minor updates:
[List files with small changes]

Create a review strategy:
1. Which files should I review in detail? (priority order)
2. Which files only need a quick scan?
3. What should I check with automated tools?
4. What requires manual validation?
5. How should I allocate my 45 minutes?

Provide a time-boxed review plan.
```

**Deliverable:** Add "Review Strategy" section to `pr-review.md`

### 6. Initial Recommendation

**Prompt your AI to:**
- Make a preliminary assessment (likely approve, likely needs changes, needs major revision)
- Identify deal-breakers vs nice-to-haves
- Set expectations for the review

**Example AI Prompt:**
```
Based on this high-level review:

[Share your findings so far]

Provide a preliminary assessment:

1. Initial recommendation (approve, request changes, needs major work)
2. Confidence level in this assessment
3. Main concerns that could change the recommendation
4. What would make this an easy approval?
5. What are the deal-breakers that must be fixed?

Note: This is preliminary - detailed review may change this.
```

**Deliverable:** Add "Preliminary Assessment" section to `pr-review.md`

## Output Format

Your `pr-review.md` should follow this structure:

```markdown
# Pull Request #127 Review

**Reviewer:** [Your Name]
**Date:** [Date]
**PR Title:** Major documentation update - new features and restructuring
**Status:** In Review

---

## PR Overview

### Summary
[2-3 sentences describing what this PR does]

### Objectives
- [Objective 1]
- [Objective 2]
- [Objective 3]

### Justification
[Why is this change needed?]

---

## Change Scope Analysis

### Changes by Type

| Type | Count | Files |
|------|-------|-------|
| New Files | 3 | tutorials/... |
| Modified Files | 8 | docs/... |
| Deleted Files | 1 | guides/legacy-setup.md |
| **Total** | **12** | |

### Change Categories
- **New Content (40%):** 3 new tutorials
- **Updates (45%):** API reference, getting started, quick start
- **Refactoring (10%):** Navigation restructuring
- **Deletions (5%):** Removing outdated content

### Scope Assessment
[Is this appropriately scoped? Too broad? Should be split?]

---

## Initial Quality Assessment

### Sample Files Reviewed
1. [File 1] - [Brief assessment]
2. [File 2] - [Brief assessment]
3. [File 3] - [Brief assessment]

### Overall Quality
- **Writing Quality:** [Rating/Description]
- **Technical Accuracy:** [Rating/Description]
- **Formatting Consistency:** [Rating/Description]
- **Completeness:** [Rating/Description]

### Observed Patterns
- [Pattern 1]
- [Pattern 2]
- [Pattern 3]

---

## Risk Areas to Review

1. **[Risk Category 1]**
   - What: [Description]
   - Why it matters: [Impact]
   - Files affected: [List]

2. **[Risk Category 2]**
   - [Similar structure]

[Continue with 5-7 risks]

---

## Review Strategy

### Priority 1: Detailed Review (30 min)
- [ ] File 1 - [Reason for priority]
- [ ] File 2 - [Reason for priority]
- [ ] File 3 - [Reason for priority]

### Priority 2: Quick Review (10 min)
- [ ] Files with minor updates
- [ ] Formatting and style consistency

### Priority 3: Automated Checks (5 min)
- [ ] Run link checker
- [ ] Run markdown linter
- [ ] Validate code examples (if possible)

### Manual Validation Required
- [ ] Cross-reference checks
- [ ] Navigation updates
- [ ] Technical accuracy of examples

---

## Preliminary Assessment

**Initial Recommendation:** [Approve / Request Changes / Needs Major Work]

**Confidence:** [High / Medium / Low]

**Main Concerns:**
1. [Concern 1]
2. [Concern 2]
3. [Concern 3]

**Potential Deal-Breakers:**
- [Issue that would block merge]
- [Another critical issue]

**Path to Approval:**
- [What needs to happen]
- [Key items to verify]

---

## Next Steps

1. Proceed with detailed content review (Task 2.2)
2. Validate cross-references (Task 2.3)
3. Compile comprehensive feedback (Task 2.4)

---

*This is a preliminary assessment based on high-level review. Detailed analysis may reveal additional issues or confirm this assessment.*
```

## Success Criteria

You've completed this task when you:

- ✅ Understand the PR's purpose and goals
- ✅ Know which files are most critical to review
- ✅ Identified potential risk areas
- ✅ Have a time-boxed review plan
- ✅ Made a preliminary recommendation
- ✅ Can explain the PR to someone else in 2 minutes

## Hints

<details>
<summary>Hint 1: Read the PR Description Carefully</summary>

The PR description (if well-written) should tell you exactly what changed and why. Use this as your anchor for reviewing if changes match intentions.
</details>

<details>
<summary>Hint 2: Use the File List as a Map</summary>

The list of changed files tells a story:
- New files = new features
- Deleted files = cleanup (watch for orphaned links!)
- Modified files = updates or fixes
- Many files in same directory = coordinated change
</details>

<details>
<summary>Hint 3: Sample, Don't Read Everything</summary>

You can't read 847 added lines in detail. Sample strategically:
- One new file (quality of new content)
- One heavily modified file (quality of updates)
- One lightly modified file (scope of changes)

Patterns you find in samples likely exist elsewhere.
</details>

<details>
<summary>Hint 4: Think About Dependencies</summary>

Ask: "If file A changes, what else should change?"
- Updated API docs → Update examples
- New tutorial → Update navigation
- Deleted file → Update all references

Missing dependent changes are a major PR issue.
</details>

## Time Management

- **Minutes 0-3:** Read PR description and understand objectives
- **Minutes 4-6:** Analyze change scope and categorize files
- **Minutes 7-10:** Spot check 2-3 files for quality
- **Minutes 11-13:** Identify risk areas and potential issues
- **Minutes 14-15:** Create review strategy and preliminary assessment

## What's Next?

After completing your high-level review, you'll move to **Task 2.2** where you'll conduct a detailed content review of the high-priority files you've identified.

---

**Need the solution?** Check [solutions/solution-2.1-initial-review.md](../solutions/solution-2.1-initial-review.md) when you're ready.
