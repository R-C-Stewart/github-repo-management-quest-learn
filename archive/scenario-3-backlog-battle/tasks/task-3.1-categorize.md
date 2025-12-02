# Task 3.1: Issue Categorization and Prioritization

**Duration:** 15 minutes
**Difficulty:** Intermediate

## Objective

Quickly categorize and prioritize all 25 issues in the backlog using AI-assisted analysis to create a manageable, organized issue tracker.

## Context

A backlog of 25+ unlabeled, unorganized issues is overwhelming and unactionable. Before you can make progress, you need to understand what you have and what matters most.

Using AI, you can categorize all issues in minutes rather than hours, then apply systematic prioritization to focus your efforts where they'll have the most impact.

## Your Challenge

Transform the chaotic backlog into a well-organized, prioritized list that guides your work and communicates status to stakeholders.

## Tasks

### 1. Bulk Issue Categorization

**Prompt your AI to:**
- Analyze all 25 issues at once
- Categorize each by type
- Assess completeness and actionability

**Example AI Prompt:**
```
Categorize these 25 GitHub issues from a documentation repository:

[For each issue, include:]
Issue #1: [Title]
Description: [Brief description]

Issue #2: [Title]
Description: [Brief description]

[Continue for all 25 issues...]

For each issue, provide in a table:
- Issue Number
- Type: bug/feature/question/typo/discussion
- Completeness: complete-info/needs-clarification/unclear
- Component: (which docs section affected)

Present as a markdown table.
```

**Deliverable:** Create `issue-categorization.md` with categorization table

### 2. Priority Assessment

**Prompt your AI to:**
- Prioritize based on user impact
- Consider effort vs value
- Identify quick wins

**Example AI Prompt:**
```
Based on these categorized issues:

[Paste your categorization table]

Assign priority levels:

**Critical (P0):** Blocks users, breaks documentation, security issues
**High (P1):** Major confusion, important missing docs, many users affected
**Medium (P2):** Improvements, nice-to-have features, affects some users
**Low (P3):** Minor polish, edge cases, very few users affected

For each issue provide:
- Priority (P0/P1/P2/P3)
- Reasoning (why this priority?)
- Estimated effort (small <1hr, medium 1-4hrs, large >4hrs)

Add these columns to the categorization table.
```

**Deliverable:** Add priority columns to `issue-categorization.md`

### 3. Identify Quick Wins

**Prompt your AI to:**
- Find high-impact, low-effort issues
- Identify issues that can be closed immediately
- Spot issues needing more information

**Example AI Prompt:**
```
From this prioritized issue list:

[Paste your table with priorities and effort]

Identify:

1. **Quick Wins** (High/Medium priority + Small effort)
   - Can be done in <1 hour
   - High impact on users
   - Should do these first

2. **Close Immediately**
   - Duplicates (handled elsewhere)
   - Wont-fix (out of scope)
   - Resolved (already done)

3. **Needs More Info**
   - Unclear what's being requested
   - Can't reproduce the issue
   - Missing context

Create three separate lists with issue numbers and brief reasoning.
```

**Deliverable:** Add "Quick Wins", "Close Immediately", and "Needs Info" sections to `issue-categorization.md`

### 4. Create a Label System

**Design GitHub labels to:**
- Support your categorization
- Enable filtering and searching
- Follow best practices

**Example AI Prompt:**
```
Based on these issue categories and priorities:

[Share your categorization findings]

Design a GitHub label system with:

1. **Type Labels**
   - Name (e.g., "bug", "enhancement")
   - Color (hex code)
   - Description
   - When to use

2. **Priority Labels**
   - Name (e.g., "P0-critical")
   - Color (red for urgent, yellow for medium, green for low)
   - Description
   - Criteria

3. **Status Labels**
   - Name (e.g., "needs-info", "in-progress")
   - Color
   - Description
   - Workflow usage

4. **Component Labels**
   - Name (which doc section)
   - Color
   - Description

Provide as a table with: Label Name, Color, Description, Example Usage
```

**Deliverable:** Create `label-system.md` with label definitions

### 5. Generate Issue Statistics

**Use AI to:**
- Calculate summary statistics
- Identify patterns in the backlog
- Create visual representations

**Example AI Prompt:**
```
From this categorized and prioritized issue backlog:

[Share your complete categorization table]

Generate statistics:

1. **Summary Counts**
   - Total issues
   - By type (bugs, features, questions, etc.)
   - By priority (P0, P1, P2, P3)
   - By effort (small, medium, large)
   - By status (actionable, needs-info, close)

2. **Patterns Analysis**
   - Which doc sections have most issues?
   - What types of issues are most common?
   - Are issues mostly quality (bugs) or growth (features)?
   - What does this tell us about documentation health?

3. **Workload Estimate**
   - Total estimated hours (by effort categories)
   - Quick wins count and hours
   - How long to clear backlog at X hours/week?

Present as tables and brief analysis.
```

**Deliverable:** Add "Backlog Statistics" section to `issue-categorization.md`

### 6. Create Action-Oriented View

**Prompt your AI to:**
- Organize issues by what action to take
- Create prioritized work lists
- Make the backlog actionable

**Example AI Prompt:**
```
Transform this categorized backlog:

[Share your table]

Into action-oriented lists:

**Week 1: Quick Wins & Critical** (Do First)
- Issue #X - [Brief description] (Est: Xh)
- Issue #Y - [Brief description] (Est: Xh)
Total: Xh

**Week 2: High Priority**
- Issue #...
Total: Xh

**Backlog: Medium Priority**
- Issue #...

**To Close/Needs Info**
- Issue #X - Close as duplicate of #Y
- Issue #Z - Request clarification on [specific point]

Make this a concrete work plan someone could execute.
```

**Deliverable:** Create `action-plan.md` with prioritized work lists

## Output Format

### issue-categorization.md

```markdown
# Issue Backlog Categorization

**Date:** [Date]
**Total Issues:** 25
**Analyzed By:** [Your Name]

---

## Categorized Issues

| # | Title | Type | Priority | Effort | Component | Status | Notes |
|---|-------|------|----------|--------|-----------|--------|-------|
| 1 | Fix broken link in installation guide | bug | P1 | small | installation | actionable | Quick win |
| 2 | Add tutorial on advanced features | feature | P2 | large | tutorials | actionable | Plan carefully |
| ... | ... | ... | ... | ... | ... | ... | ... |

---

## Summary Statistics

### By Type
- 🐛 Bugs: 8 (32%)
- ✨ Features: 7 (28%)
- ❓ Questions: 4 (16%)
- ✏️ Typos: 3 (12%)
- 💬 Discussions: 3 (12%)

### By Priority
- P0 Critical: 2
- P1 High: 7
- P2 Medium: 11
- P3 Low: 5

### By Effort
- Small (<1hr): 8 issues
- Medium (1-4hrs): 12 issues
- Large (>4hrs): 5 issues

### By Status
- Actionable: 18
- Needs Info: 4
- Should Close: 3

---

## Quick Wins (High Impact, Low Effort)

1. **Issue #X** - [Description] - P1, Est: 30min
   - Why it matters: [Impact]
   - What to do: [Action]

2. **Issue #Y** - [Description] - P2, Est: 45min
   - Why it matters: [Impact]
   - What to do: [Action]

[Continue...]

**Total Quick Win Hours:** ~4-5 hours (could clear 8 issues this week!)

---

## Close Immediately

1. **Issue #X** - Duplicate of #Y
   - Response: "Closing as duplicate of #Y which addresses this. See [link]."

2. **Issue #Z** - Already resolved in [PR/commit]
   - Response: "This was addressed in [link]. Thanks for reporting!"

---

## Needs More Information

1. **Issue #X** - [Title]
   - What's unclear: [Specific questions]
   - What to ask: "[Draft question]"

---

## Patterns & Insights

### Most Affected Sections
1. Installation docs - 6 issues
2. API reference - 5 issues
3. Tutorials - 4 issues

### Root Cause Analysis
- Many broken links → Suggests recent restructuring or inadequate link checking
- Multiple "How do I..." questions → Gaps in tutorials
- Several typos → Need spell-check in CI/CD

### Recommendations
1. Add automated link checking
2. Create "Common Tasks" tutorial section
3. Implement spell-check pre-commit hook
4. Document the API examples better

---

## Workload Estimate

- **Quick Wins (8 issues):** 4-5 hours
- **High Priority (7 issues):** 15-20 hours
- **Medium Priority (11 issues):** 25-35 hours
- **Low Priority (5 issues):** 10-15 hours

**Total Estimated Effort:** 55-75 hours

**At 5 hours/week:** 11-15 weeks to clear backlog
**At 10 hours/week:** 6-8 weeks to clear backlog

---

*Next Steps: See action-plan.md for execution roadmap*
```

### label-system.md

```markdown
# GitHub Label System for Documentation Repository

## Type Labels

| Label | Color | Description | When to Use |
|-------|-------|-------------|-------------|
| `bug` | #d73a4a | Something is broken or incorrect | Broken links, incorrect info, errors |
| `enhancement` | #a2eeef | New feature or improvement | New tutorials, expanded sections |
| `question` | #d876e3 | User question or help request | "How do I..." questions |
| `documentation` | #0075ca | Documentation meta issue | Process, standards, structure |
| `typo` | #fbca04 | Spelling or grammar fix | Simple text corrections |

## Priority Labels

| Label | Color | Description | Criteria |
|-------|-------|-------------|----------|
| `P0-critical` | #b60205 | Urgent, blocks users | Broken installation, incorrect commands |
| `P1-high` | #d93f0b | Important, fix soon | Major confusion, missing key docs |
| `P2-medium` | #fbca04 | Should fix | Improvements, nice-to-haves |
| `P3-low` | #0e8a16 | Low priority | Minor polish, edge cases |

## Status Labels

| Label | Color | Description | Usage |
|-------|-------|-------------|-------|
| `needs-info` | #ffffff | Awaiting reporter response | Unclear issues, can't reproduce |
| `in-progress` | #c5def5 | Currently being worked on | Assigned and active |
| `blocked` | #e99695 | Can't proceed | Waiting on dependency |
| `duplicate` | #cfd3d7 | Already reported elsewhere | Link to original issue |
| `wont-fix` | #000000 | Won't implement | Out of scope, by design |

## Component Labels

| Label | Color | Description |
|-------|-------|-------------|
| `area:installation` | #bfd4f2 | Installation documentation |
| `area:api` | #bfd4f2 | API reference docs |
| `area:tutorials` | #bfd4f2 | Tutorial content |
| `area:guides` | #bfd4f2 | How-to guides |
| `area:navigation` | #bfd4f2 | Site structure, menus |

## Special Labels

| Label | Color | Description |
|-------|-------|-------------|
| `good-first-issue` | #7057ff | Easy for new contributors |
| `help-wanted` | #008672 | Need community help |
| `quick-win` | #5319e7 | Small effort, high impact |

## Label Usage Guidelines

### When Creating an Issue
1. Apply one type label (bug, enhancement, etc.)
2. Apply one priority label (P0-P3)
3. Apply component labels as needed
4. Consider status labels if appropriate

### During Triage
1. Validate or update type/priority
2. Add component labels
3. Add status labels (needs-info, etc.)
4. Add special labels (good-first-issue, etc.)

### When Working on Issue
1. Add `in-progress` label
2. Assign to yourself
3. Update milestone if applicable

### When Closing
1. Add resolution label if needed (duplicate, wont-fix)
2. Remove `in-progress`
3. Ensure comment explains closure
```

### action-plan.md

```markdown
# Issue Backlog Action Plan

**Created:** [Date]
**Status:** Ready to Execute
**Total Issues:** 25
**Estimated Total Effort:** 55-75 hours

---

## Phase 1: Quick Wins (Week 1)

**Goal:** Clear easy issues, show progress, build momentum
**Estimated Time:** 4-5 hours
**Issues:** 8

### Priority Order

1. ✏️ **Issue #X** - Fix typo in getting started (5 min)
2. 🐛 **Issue #Y** - Fix broken link in installation.md (15 min)
3. ✏️ **Issue #Z** - Correct code example syntax (20 min)
4. 🐛 **Issue #...** - Update outdated version number (10 min)
5. 🐛 **Issue #...** - Fix incorrect command (15 min)
6. ✏️ **Issue #...** - Grammar fix in API docs (5 min)
7. 🐛 **Issue #...** - Add missing alt text to image (20 min)
8. 🐛 **Issue #...** - Fix relative link path (10 min)

**Success Criteria:** 8 issues closed, 32% of backlog cleared

---

## Phase 2: Critical & High Priority (Weeks 2-3)

**Goal:** Address issues causing user pain
**Estimated Time:** 15-20 hours
**Issues:** 7 (2 critical + 5 high)

### Critical (P0) - Week 2

1. 🐛 **Issue #X** - Installation instructions don't work on Windows (3h)
   - Action: Test and update installation guide
   - Impact: Blocks 40% of users

2. 🐛 **Issue #Y** - API example returns 404 error (2h)
   - Action: Update API endpoint, verify all examples
   - Impact: Breaks getting started experience

### High Priority (P1) - Week 3

3. ✨ **Issue #...** - Add authentication tutorial (4h)
   - Action: Write new tutorial
   - Impact: Top requested feature

4. 🐛 **Issue #...** - Navigation broken on mobile (3h)
   - Action: Fix responsive navigation
   - Impact: 25% of traffic is mobile

5. ❓ **Issue #...** - How to handle errors? (2h)
   - Action: Add error handling section to docs
   - Impact: Frequent support question

6. 🐛 **Issue #...** - Incomplete API parameters table (2h)
   - Action: Complete documentation
   - Impact: Developers can't use API

7. ✨ **Issue #...** - Add troubleshooting guide (3h)
   - Action: Create troubleshooting doc from support tickets
   - Impact: Reduce support load

**Success Criteria:** All blockers removed, major gaps filled

---

## Phase 3: Medium Priority (Weeks 4-6)

**Goal:** Improve documentation quality and completeness
**Estimated Time:** 25-35 hours
**Issues:** 11

### Features & Enhancements (8 issues)

1. ✨ **Issue #X** - Add advanced configuration guide (5h)
2. ✨ **Issue #Y** - Expand API examples (4h)
3. ✨ **Issue #Z** - Create video tutorials (8h)
4. ✨ **Issue #...** - Add deployment guide (6h)
5. 💬 **Issue #...** - Reorganize documentation structure (5h)
6. ✨ **Issue #...** - Add FAQ section (3h)
7. ✨ **Issue #...** - Create cheat sheet (2h)
8. 💬 **Issue #...** - Add search functionality discussion (2h)

### Bugs & Improvements (3 issues)

9. 🐛 **Issue #...** - Inconsistent terminology (3h)
10. 🐛 **Issue #...** - Missing prerequisites in tutorial (2h)
11. 🐛 **Issue #...** - Outdated screenshots (4h)

**Success Criteria:** Documentation is comprehensive, polished

---

## Phase 4: Low Priority / Backlog

**Goal:** Polish and edge cases
**Estimated Time:** 10-15 hours
**Issues:** 5

1. 💬 **Issue #X** - Consider dark mode for docs site (4h)
2. ✨ **Issue #Y** - Add PDF export option (3h)
3. 🐛 **Issue #Z** - Minor formatting inconsistency (1h)
4. ❓ **Issue #...** - Clarification on edge case (2h)
5. ✨ **Issue #...** - Add more code examples (5h)

**Priority:** Work on these when high-priority work is complete

---

## Issues to Close (3 issues)

### Immediate Closure

1. **Issue #X** - Duplicate of #Y
   - Action: Close with comment linking to #Y
   - Response: "Thanks for reporting! This is tracked in #Y."

2. **Issue #Z** - Already fixed in PR #123
   - Action: Close with reference to PR
   - Response: "Fixed in PR #123, will be in next release."

3. **Issue #W** - Out of scope
   - Action: Close as wont-fix with explanation
   - Response: "Thanks for the suggestion! This is outside the scope of our documentation. Consider [alternative]."

---

## Issues Needing Clarification (4 issues)

1. **Issue #X** - Vague feature request
   - Question: "Can you provide more details on what you're trying to accomplish?"
   - Label: `needs-info`

2. **Issue #Y** - Can't reproduce bug
   - Question: "What OS and version are you using? Can you provide the exact error message?"
   - Label: `needs-info`

3. **Issue #Z** - Unclear what's being requested
   - Question: "Are you asking about [A] or [B]? An example would help."
   - Label: `needs-info`

4. **Issue #W** - Missing context
   - Question: "Which documentation page is this about? A link would be helpful."
   - Label: `needs-info`

---

## Execution Strategy

### Week 1: Build Momentum
- ✅ Complete all 8 quick wins (1 hour per day)
- ✅ Close 3 issues immediately
- ✅ Request info on 4 issues
- **Result:** Backlog down to 10 actionable issues

### Weeks 2-3: Critical Path
- ✅ Clear critical blockers
- ✅ Address high-priority issues
- **Result:** No urgent issues remaining

### Weeks 4-6: Quality Improvement
- ✅ Work through medium-priority enhancements
- ✅ Build out missing documentation
- **Result:** Comprehensive, quality documentation

### Ongoing: Maintenance
- ✅ Low-priority items as time permits
- ✅ Monitor new issues, triage weekly
- **Result:** Sustainable backlog management

---

## Success Metrics

**After Phase 1 (Week 1):**
- ✅ 68% of backlog remains (down from 100%)
- ✅ All simple fixes complete
- ✅ Clear direction for remaining work

**After Phase 2 (Week 3):**
- ✅ No critical or high-priority issues
- ✅ User pain points addressed
- ✅ Support tickets reduced

**After Phase 3 (Week 6):**
- ✅ Only 5 low-priority issues remain
- ✅ Documentation is comprehensive
- ✅ Sustainable process established

---

## Process Improvements

To prevent future backlog accumulation:

1. **Implement triage process** (see issue templates)
2. **Weekly review** of new issues
3. **Label all issues** within 48 hours
4. **Close stale issues** after 30 days of no response
5. **Track metrics** (time to first response, resolution time)
6. **Automated checks** (prevent bugs from becoming issues)

---

*This plan is realistic and actionable. Adjust timeline based on team capacity.*
```

## Success Criteria

You've completed this task when you:

- ✅ Categorized all 25 issues by type, priority, effort, and status
- ✅ Identified 5-8 quick wins that can be done immediately
- ✅ Found 2-3 issues to close immediately
- ✅ Flagged issues needing more information
- ✅ Designed a comprehensive label system
- ✅ Created actionable work plan with realistic timeline
- ✅ Generated insightful statistics and patterns

## Hints

<details>
<summary>Hint 1: Categorize in Bulk</summary>

Don't analyze issues one by one. Share all 25 with your AI at once and ask for a complete categorization table. This is 10x faster and ensures consistency.
</details>

<details>
<summary>Hint 2: Priority Framework</summary>

Use this simple framework:
- **Impact:** How many users affected? How severe?
- **Effort:** How long to fix?
- **Dependencies:** Blocks other work?

High impact + Low effort = Quick win
High impact + High effort = Important but plan carefully
Low impact + Low effort = Do if time permits
Low impact + High effort = Backlog or decline
</details>

<details>
<summary>Hint 3: Be Ruthless About Closing</summary>

Not every issue deserves action:
- Duplicates → Close
- Already fixed → Close
- Out of scope → Politely close with explanation
- Too vague after asking for info → Close after 30 days

A clean backlog is better than a large backlog.
</details>

<details>
<summary>Hint 4: Label Colors Matter</summary>

Use color psychology:
- Red: Urgent/Critical
- Yellow/Orange: Important
- Green: Low priority/good to go
- Blue: Informational/neutral
- Purple: Special categories

Consistent colors help quick visual scanning.
</details>

## Time Management

- **Minutes 0-4:** Bulk categorize all issues by type
- **Minutes 5-8:** Assign priorities and effort estimates
- **Minutes 9-11:** Identify quick wins and closures
- **Minutes 12-14:** Design label system
- **Minutes 14-15:** Generate statistics and review

## What's Next?

After categorizing your backlog, you'll move to **Task 3.2** where you'll identify relationships, duplicates, and dependencies between issues.

---

**Need the solution?** Check [solutions/solution-3.1-categorize.md](../solutions/solution-3.1-categorize.md) when you're ready.
