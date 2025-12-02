# Task 3.3: Create Issue Templates and Labels

**Duration:** 15 minutes
**Difficulty:** Intermediate

## Objective

Establish systems (templates, labels, and processes) that prevent future backlog chaos and improve issue quality.

## Context

The current backlog is chaotic partly because there were no systems in place. Issues lack important information, aren't labeled, and follow no consistent format.

By creating templates and processes now, you prevent the next backlog crisis.

## Your Challenge

Create reusable templates, implement your label system, and document the triage process.

## Tasks

### 1. Create Bug Report Template

**Example AI Prompt:**
```
Create a GitHub issue template for bug reports in a documentation repository.

Include sections for:
1. Bug description
2. Which documentation page/section
3. What's incorrect or broken
4. Expected vs actual
5. Browser/environment (if relevant)
6. Screenshots (optional)
7. Additional context

Format as GitHub issue template YAML for .github/ISSUE_TEMPLATE/
```

**Deliverable:** Create `bug-report-template.yml`

### 2. Create Feature Request Template

**Example AI Prompt:**
```
Create a GitHub issue template for documentation feature requests.

Include sections for:
1. What documentation is missing or needed
2. Who needs this (audience)
3. Why it's important (use case)
4. Example of what you want to see
5. Any existing workarounds
6. Additional context

Format as GitHub issue template YAML
```

**Deliverable:** Create `feature-request-template.yml`

### 3. Create Question Template

**Example AI Prompt:**
```
Create a GitHub issue template for user questions about documentation.

Include:
1. What are you trying to do?
2. What documentation did you check?
3. What specifically is unclear?
4. What would make this clearer?

Add note suggesting community forum for general questions.

Format as GitHub issue template YAML
```

**Deliverable:** Create `question-template.yml`

### 4. Create Triage Process Documentation

**Example AI Prompt:**
```
Create documentation for triaging new issues in our documentation repository.

Include:
1. Who does triage (maintainers? Rotating duty?)
2. When (daily? Weekly? On notification?)
3. Steps to triage each new issue:
   - Read and understand
   - Apply type label
   - Apply priority label
   - Apply component label
   - Add to project/milestone if appropriate
   - Respond with acknowledgment
   - Assign if possible
4. Response time SLA (e.g., first response within 48 hours)
5. Escalation (what qualifies as urgent)
6. Examples of good triage

Format as CONTRIBUTING.md section
```

**Deliverable:** Create `triage-process.md`

### 5. Create Response Templates

**Example AI Prompt:**
```
Create saved reply templates for common issue responses:

1. **Closing as duplicate**
   - Polite acknowledgment
   - Link to original issue
   - Invite to subscribe

2. **Needs more information**
   - Thank reporter
   - Specific questions to clarify
   - Timeline for response

3. **Out of scope / Won't fix**
   - Thank for suggestion
   - Explain why out of scope
   - Suggest alternatives

4. **Fixed / Already resolved**
   - Confirm resolution
   - Link to fix (PR/commit)
   - When available

5. **Good first issue**
   - Thank for report
   - Invite to contribute
   - Link to CONTRIBUTING.md

Provide as markdown templates
```

**Deliverable:** Create `response-templates.md`

### 6. Implement Label System

Using the label system from Task 3.1:

**Create `labels.yml` file with:**
```yaml
# Type Labels
- name: bug
  description: Something is broken or incorrect
  color: d73a4a

- name: enhancement
  description: New feature or improvement
  color: a2eeef

[Continue for all labels...]
```

**Deliverable:** Create `labels.yml` configuration file

## Output Format

### .github/ISSUE_TEMPLATE/bug-report.yml

```yaml
name: Bug Report
description: Report a problem with the documentation
title: "[BUG] "
labels: ["bug"]
body:
  - type: markdown
    attributes:
      value: |
        Thanks for taking the time to report a documentation bug!

  - type: input
    id: location
    attributes:
      label: Documentation Location
      description: Which page or section has the issue?
      placeholder: "e.g., Installation Guide - Step 3"
    validations:
      required: true

  - type: textarea
    id: description
    attributes:
      label: What's Wrong?
      description: Clearly describe what's incorrect or broken
      placeholder: "The installation command doesn't work..."
    validations:
      required: true

  - type: textarea
    id: expected
    attributes:
      label: What Should It Say?
      description: What's the correct information or expected behavior?
    validations:
      required: false

  - type: dropdown
    id: severity
    attributes:
      label: Impact
      description: How much does this affect users?
      options:
        - Critical (blocks users)
        - High (causes significant confusion)
        - Medium (inconvenient but has workaround)
        - Low (minor issue)
    validations:
      required: true

  - type: textarea
    id: context
    attributes:
      label: Additional Context
      description: Screenshots, error messages, or other helpful info
    validations:
      required: false
```

### .github/ISSUE_TEMPLATE/feature-request.yml

```yaml
name: Documentation Request
description: Request new or improved documentation
title: "[REQUEST] "
labels: ["enhancement"]
body:
  - type: markdown
    attributes:
      value: |
        Thanks for suggesting how we can improve our documentation!

  - type: textarea
    id: need
    attributes:
      label: What Documentation is Needed?
      description: What would you like to see documented?
      placeholder: "A tutorial on..."
    validations:
      required: true

  - type: textarea
    id: usecase
    attributes:
      label: Why is This Important?
      description: What are you trying to accomplish?
      placeholder: "I'm trying to..."
    validations:
      required: true

  - type: input
    id: audience
    attributes:
      label: Target Audience
      description: Who needs this? (beginners, advanced users, etc.)
      placeholder: "e.g., New users during onboarding"

  - type: textarea
    id: example
    attributes:
      label: Example or Structure
      description: Do you have an example of what you'd like to see?
    validations:
      required: false

  - type: textarea
    id: workaround
    attributes:
      label: Current Workaround
      description: How are you handling this currently?
    validations:
      required: false
```

### triage-process.md

```markdown
# Issue Triage Process

## Purpose

Ensure all issues are properly categorized, prioritized, and responded to in a timely manner.

## Roles & Responsibilities

**Triage Team:** All documentation maintainers
**Schedule:** Daily check for new issues (or configure notifications)
**SLA:** First response within 48 hours (24h for critical issues)

## Triage Steps

### 1. Initial Review (2-3 minutes per issue)

**Read the issue carefully:**
- What is being reported/requested?
- Is the description clear and complete?
- Is this actually a documentation issue?

### 2. Validate & Clarify

**Ask yourself:**
- Can I reproduce this (for bugs)?
- Is this a duplicate of existing issue?
- Is this in scope for our documentation?
- Is there enough information to act?

**If unclear:** Request more information using response template

### 3. Apply Labels

**Apply in this order:**

1. **Type Label** (required - choose one)
   - `bug` - Something is wrong
   - `enhancement` - New or improved docs
   - `question` - User question
   - `documentation` - Meta issue about docs process
   - `typo` - Simple text correction

2. **Priority Label** (required - choose one)
   - `P0-critical` - Blocks users, urgent
   - `P1-high` - Important, affects many users
   - `P2-medium` - Should fix, moderate impact
   - `P3-low` - Nice to have, low impact

3. **Component Label** (as appropriate)
   - `area:installation`
   - `area:api`
   - `area:tutorials`
   - `area:guides`

4. **Status Labels** (if applicable)
   - `needs-info` - Waiting for reporter
   - `good-first-issue` - Good for new contributors
   - `help-wanted` - Need community help

### 4. Assess Priority

Use this framework:

**P0 - Critical:**
- Incorrect commands that break installations
- Security issues in documentation
- Broken core workflows
- Anything blocking users completely

**P1 - High:**
- Major confusion or missing key documentation
- Affects significant portion of users
- Frequently asked questions
- Important missing tutorials

**P2 - Medium:**
- Improvements to existing docs
- Nice-to-have features
- Affects some users
- Non-urgent bugs with workarounds

**P3 - Low:**
- Minor polish items
- Edge cases
- Affects very few users
- Cosmetic issues

### 5. Respond

**Always acknowledge the issue within SLA:**

**Good acknowledgment:**
> Thanks for reporting this! I've labeled this as [priority] and [type]. We'll [plan to address/need more info/add to backlog]. Expected timeline: [estimate or "will update soon"].

**For duplicates:**
> Thanks! This is a duplicate of #X which we're tracking. Closing this one, but please feel free to add any additional context to #X.

**For out-of-scope:**
> Thanks for the suggestion! This is outside the scope of our documentation, but you might find [alternative resource] helpful. Closing as won't-fix.

**For needs-info:**
> Thanks for reporting! To help us address this, could you provide:
> 1. [Specific question]
> 2. [Specific question]
> We'll follow up once we have this information.

### 6. Assign (if possible)

- **Self-assign** if you can fix quickly (<1 hour)
- **Assign to expert** if it requires specific knowledge
- **Leave unassigned** and add to project board for team planning

### 7. Add to Planning

- **Critical:** Add to current sprint/milestone
- **High:** Add to next sprint/milestone
- **Medium/Low:** Add to backlog

## Examples

### Example 1: Good Bug Report

**Issue:** "Installation command fails on Windows"
**Triage Action:**
- ✅ Apply labels: `bug`, `P1-high`, `area:installation`
- ✅ Confirm bug affects Windows users
- ✅ Respond: "Confirmed - testing fix now. Should have update within 24h."
- ✅ Self-assign and add to current sprint
- ✅ Fix within 24h

### Example 2: Vague Feature Request

**Issue:** "Need better docs"
**Triage Action:**
- ✅ Apply label: `needs-info`
- ✅ Respond: "Thanks! Can you help us understand what documentation would be most helpful? What are you trying to accomplish?"
- ✅ Set reminder to close if no response in 30 days

### Example 3: Duplicate

**Issue:** "Broken link in getting started"
**Triage Action:**
- ✅ Search for existing issues about same link
- ✅ Find issue #45 already tracks this
- ✅ Apply label: `duplicate`
- ✅ Respond: "Thanks! This is tracked in #45. Closing as duplicate."
- ✅ Close immediately

## Common Triage Mistakes

❌ **Don't:**
- Skip labeling (all issues need at least type + priority)
- Ignore issues (respond even if you can't fix immediately)
- Over-promise timelines (under-promise, over-deliver)
- Be rude or dismissive (even to low-quality issues)

✅ **Do:**
- Label consistently
- Respond professionally
- Set realistic expectations
- Thank reporters (they're helping!)

## Triage Metrics

Track these to measure process health:
- **Time to first response:** Avg time from issue opened to first comment
- **Triage coverage:** % of issues labeled within 48h
- **Backlog growth:** New issues vs closed issues per week
- **Stale issues:** Issues open >90 days with no activity

**Target SLAs:**
- First response: <48h (95% of issues)
- Labeling: <24h (100% of issues)
- Critical issues: <4h first response

## Monthly Triage Review

Once per month, review:
1. Open issues without labels → Triage
2. `needs-info` issues >30 days old → Close with note
3. Stale issues (>90 days, no activity) → Close or re-prioritize
4. Label usage patterns → Adjust labels if needed
5. Response time metrics → Improve process if needed

---

**Remember:** Good triage helps the team work efficiently and makes contributors feel valued!
```

### response-templates.md

```markdown
# Issue Response Templates

Saved replies for common scenarios. Use as-is or customize.

## Closing as Duplicate

```markdown
Thanks for reporting this! This is a duplicate of #[ISSUE_NUMBER] which we're actively tracking.

I'm closing this issue to consolidate discussion, but please feel free to:
- Subscribe to #[ISSUE_NUMBER] for updates
- Add any additional context there if you have unique details

Thanks for helping us improve the documentation!
```

## Needs More Information

```markdown
Thanks for taking the time to report this!

To help us address this issue, could you provide some additional details:

1. [SPECIFIC_QUESTION_1]
2. [SPECIFIC_QUESTION_2]
3. [SPECIFIC_QUESTION_3]

We'll follow up once we have this information. If we don't hear back within 30 days, we'll close this issue, but you're welcome to reopen it anytime with the requested details.
```

## Out of Scope / Won't Fix

```markdown
Thanks for the suggestion!

After team discussion, we've decided this is outside the scope of our documentation because [REASON]:
- [SPECIFIC_REASON_1]
- [SPECIFIC_REASON_2]

However, you might find these alternatives helpful:
- [ALTERNATIVE_1]
- [ALTERNATIVE_2]

We're closing this as won't-fix, but we appreciate you taking the time to suggest improvements!
```

## Already Fixed

```markdown
Great catch! This issue was resolved in [PR_NUMBER / COMMIT_HASH].

The fix is:
- ✅ Merged to main
- ✅ Deployed to [DOCS_SITE]
- ✅ Available as of [DATE]

You can see the updated documentation at [LINK].

Thanks for reporting this!
```

## Good First Issue - Inviting Contribution

```markdown
Thanks for reporting this! This looks like a good opportunity for a community contribution.

Would you be interested in submitting a fix? Here's how to get started:

1. Check our [CONTRIBUTING.md](link) for guidelines
2. Fork the repository
3. Make your changes following our [documentation standards](link)
4. Submit a pull request

We're here to help if you have questions! If you'd prefer not to contribute, we'll add this to our backlog.

I'm labeling this as `good-first-issue` and `help-wanted`.
```

## Stale Issue Closure

```markdown
This issue has been open for 90+ days without activity. To keep our backlog manageable, we're closing this issue.

If this is still relevant, please feel free to:
- Reopen this issue with updated information
- Create a new issue with current details

Thanks!
```

## Acknowledge High Priority

```markdown
Thanks for reporting this! I can see this is affecting [USER_GROUP] and is [BLOCKING/CAUSING_CONFUSION/etc].

I've labeled this as `P1-high` and added it to our [current sprint/next sprint].

Expected timeline: [TIMELINE]
We'll update this issue as we make progress.

Thanks for bringing this to our attention!
```

## Question Answered

```markdown
Thanks for your question!

[ANSWER_TO_QUESTION]

Does this address your question? If not, please let us know what's still unclear and we'll follow up.

We're also adding a note to improve the documentation in this area so future users don't hit the same confusion.

Related documentation:
- [LINK_1]
- [LINK_2]
```

## Feature Request - Needs Discussion

```markdown
Thanks for the suggestion! This is an interesting idea.

Before we proceed, we'd like to gather more input:
- [QUESTION_FOR_COMMUNITY]
- [QUESTION_FOR_COMMUNITY]

I'm adding the `discussion` label and we'll use this thread to gather feedback.

If others are interested in this, please 👍 the original post and share your use case!
```

---

## Tips for Using Templates

1. **Customize:** Always personalize with specifics from the issue
2. **Be genuine:** Templates should sound human, not robotic
3. **Add context:** Include relevant links and references
4. **Set expectations:** Give timelines when possible
5. **Thank reporters:** Always acknowledge their effort

## When NOT to Use Templates

- Complex, nuanced situations
- Sensitive issues
- When relationship-building is important
- First-time major contributor

In these cases, write a custom response showing you've invested time understanding the issue.
```

### labels.yml

```yaml
# GitHub Labels Configuration
# Apply with: gh label sync -f labels.yml

# Type Labels
- name: bug
  description: "Something is broken or incorrect"
  color: "d73a4a"

- name: enhancement
  description: "New feature or improvement"
  color: "a2eeef"

- name: question
  description: "User question or help request"
  color: "d876e3"

- name: documentation
  description: "Documentation meta issue"
  color: "0075ca"

- name: typo
  description: "Spelling or grammar fix"
  color: "fbca04"

# Priority Labels
- name: P0-critical
  description: "Urgent - blocks users"
  color: "b60205"

- name: P1-high
  description: "Important - fix soon"
  color: "d93f0b"

- name: P2-medium
  description: "Should fix"
  color: "fbca04"

- name: P3-low
  description: "Low priority"
  color: "0e8a16"

# Status Labels
- name: needs-info
  description: "Awaiting reporter response"
  color: "ffffff"

- name: in-progress
  description: "Currently being worked on"
  color: "c5def5"

- name: blocked
  description: "Can't proceed - dependency"
  color: "e99695"

- name: duplicate
  description: "Already reported elsewhere"
  color: "cfd3d7"

- name: wont-fix
  description: "Won't implement"
  color: "000000"

# Component Labels
- name: area:installation
  description: "Installation documentation"
  color: "bfd4f2"

- name: area:api
  description: "API reference docs"
  color: "bfd4f2"

- name: area:tutorials
  description: "Tutorial content"
  color: "bfd4f2"

- name: area:guides
  description: "How-to guides"
  color: "bfd4f2"

- name: area:navigation
  description: "Site structure, menus"
  color: "bfd4f2"

# Special Labels
- name: good-first-issue
  description: "Easy for new contributors"
  color: "7057ff"

- name: help-wanted
  description: "Need community help"
  color: "008672"

- name: quick-win
  description: "Small effort, high impact"
  color: "5319e7"
```

## Success Criteria

- ✅ Created 3+ issue templates for common scenarios
- ✅ Documented complete triage process
- ✅ Created 8+ response templates
- ✅ Implemented label system configuration
- ✅ Templates are clear and professional
- ✅ Process is realistic and sustainable

## Hints

<details>
<summary>Hint 1: Keep Templates Simple</summary>

Templates should guide reporters, not overwhelm them. Ask for essential information only. Optional fields are okay for "nice to have" details.
</details>

<details>
<summary>Hint 2: Test Your Templates</summary>

Create a test issue using each template to ensure the formatting works and questions make sense.
</details>

<details>
<summary>Hint 3: Make Process Sustainable</summary>

Don't create processes that require heroic effort. If triage takes >5 minutes per issue, simplify.
</details>

## Time Management

- **Minutes 0-5:** Create issue templates
- **Minutes 6-10:** Write triage process documentation
- **Minutes 11-14:** Create response templates
- **Minutes 14-15:** Create labels configuration

## What's Next?

Move to **Task 3.4** to draft actual responses for your backlog issues and create the final execution plan.

---

**Need the solution?** Check [solutions/solution-3.3-templates.md](../solutions/solution-3.3-templates.md)
