# Task 1.4: Documentation Standards Document

**Duration:** 15 minutes
**Difficulty:** Intermediate

## Objective

Create a comprehensive documentation standards guide that will prevent future quality issues and ensure consistency across the TechFlow repository.

## Context

You've identified numerous issues in the repository, many of which could have been prevented with clear standards and guidelines. Now it's time to create those standards so this doesn't happen again.

This document will serve as:
- A guide for contributors
- A checklist for reviewers
- The basis for automated quality checks
- The foundation for your documentation culture

## Your Challenge

Create a `DOCUMENTATION_STANDARDS.md` file that establishes clear, actionable standards for all documentation in this repository.

## Tasks

### 1. Define Markdown Formatting Standards

**Prompt your AI to:**
- Establish consistent heading conventions
- Define code block formatting rules
- Specify list and table formatting
- Set link formatting standards

**Example AI Prompt:**
```
Create a "Markdown Formatting Standards" section for our documentation guide.

Include rules for:
1. Heading levels (when to use #, ##, ###, etc.)
2. Heading capitalization (title case vs sentence case)
3. Code block syntax (always use ``` with language specifier)
4. List formatting (when to use bullets vs numbers, indentation)
5. Table formatting (alignment, header rows)
6. Link formatting (relative vs absolute, inline vs reference)
7. Emphasis (when to use bold vs italic)
8. Line length recommendations

For each rule, provide:
- The standard
- Why it matters
- A correct example
- An incorrect example

Keep it practical and easy to follow.
```

**Deliverable:** Add "Markdown Formatting Standards" section to `DOCUMENTATION_STANDARDS.md`

### 2. Establish Content Structure Standards

**Prompt your AI to:**
- Define required sections for different document types
- Create templates for common documents
- Specify metadata requirements
- Establish file organization rules

**Example AI Prompt:**
```
Create a "Content Structure Standards" section that defines:

1. Required sections for each document type:
   - Tutorials (Introduction, Prerequisites, Steps, Troubleshooting, Next Steps)
   - API References (Overview, Endpoints, Parameters, Examples, Errors)
   - How-to Guides (Goal, Prerequisites, Steps, Verification)
   - Conceptual Docs (Overview, Key Concepts, Use Cases, Related Topics)

2. File organization rules:
   - Naming conventions (lowercase, hyphens, descriptive)
   - Directory structure
   - Where different types of docs belong

3. Metadata requirements:
   - What frontmatter or header info to include
   - Last updated dates
   - Author/owner information

Provide templates for each document type.
```

**Deliverable:** Add "Content Structure Standards" section to `DOCUMENTATION_STANDARDS.md`

### 3. Define Quality Requirements

**Prompt your AI to:**
- Establish link checking requirements
- Define technical accuracy standards
- Specify image and asset requirements
- Set accessibility requirements

**Example AI Prompt:**
```
Create a "Quality Requirements" section that establishes:

1. Link Checking:
   - All links must be validated before merging
   - Internal links should use relative paths
   - External links should be periodically reviewed
   - Broken link checking should be automated

2. Technical Accuracy:
   - Code examples must be tested
   - Version numbers must be current
   - Commands must be verified to work
   - Screenshots should match current UI

3. Images and Assets:
   - All images must have alt text
   - File size limits
   - Acceptable formats
   - Naming conventions
   - Where to store assets

4. Accessibility:
   - Clear headings hierarchy
   - Descriptive link text (no "click here")
   - Alt text for images
   - Readable font sizes and contrast

Provide specific, testable criteria for each requirement.
```

**Deliverable:** Add "Quality Requirements" section to `DOCUMENTATION_STANDARDS.md`

### 4. Create a Review and Approval Process

**Prompt your AI to:**
- Define the documentation review workflow
- Establish reviewer responsibilities
- Create a review checklist
- Set merge criteria

**Example AI Prompt:**
```
Create a "Review and Approval Process" section that defines:

1. Who reviews documentation?
   - Peer review requirements
   - Subject matter expert review (when needed)
   - Technical writer review (if applicable)

2. Review workflow:
   - Create branch
   - Make changes
   - Self-review checklist
   - Submit PR
   - Address feedback
   - Merge requirements

3. Reviewer checklist:
   - [ ] Follows formatting standards
   - [ ] Content is accurate
   - [ ] Links work
   - [ ] Images have alt text
   - [ ] Code examples are tested
   - [ ] Spelling and grammar checked
   - [ ] Appropriate for audience
   - [Add more items based on our standards]

4. Merge criteria:
   - Must pass automated checks
   - Must have approving review
   - No unresolved comments
   - Follows all standards

Make this practical and not overly bureaucratic.
```

**Deliverable:** Add "Review and Approval Process" section to `DOCUMENTATION_STANDARDS.md`

### 5. Define Style and Voice Guidelines

**Prompt your AI to:**
- Establish tone and voice
- Create terminology standards
- Define writing style guidelines
- Provide examples of good vs bad writing

**Example AI Prompt:**
```
Create a "Style and Voice Guidelines" section that defines:

1. Tone and Voice:
   - Professional but approachable
   - Active voice preferred
   - Second person ("you") for user-facing docs
   - Clear and concise

2. Terminology:
   - Preferred terms vs deprecated terms
   - Consistent naming for product features
   - Acronyms (spell out on first use)
   - Technical jargon (avoid or explain)

3. Writing Style:
   - Sentence structure (clear subject-verb-object)
   - Paragraph length (3-5 sentences)
   - Use of examples
   - Step numbering conventions

4. Common Pitfalls to Avoid:
   - Passive voice
   - Ambiguous pronouns
   - Overly complex sentences
   - Unexplained jargon

Provide before/after examples showing improvements.
```

**Deliverable:** Add "Style and Voice Guidelines" section to `DOCUMENTATION_STANDARDS.md`

### 6. Specify Tools and Automation

**Prompt your AI to:**
- Recommend specific tools
- Define automation requirements
- Provide setup instructions
- Link tools to standards

**Example AI Prompt:**
```
Create a "Tools and Automation" section that specifies:

1. Required Tools:
   - Markdown linter (markdownlint) - enforces formatting
   - Link checker (specific tool) - validates links
   - Spell checker - catches typos
   - [Other tools based on our standards]

2. Recommended Tools:
   - VS Code extensions for documentation
   - AI assistants for writing and review
   - Screenshot tools with annotation

3. Automation Setup:
   - Pre-commit hooks (what to check locally)
   - CI/CD checks (what to check on PR)
   - Scheduled jobs (periodic link checking)

4. Configuration:
   - Provide config files for each tool
   - Link to setup instructions
   - Explain what each check does

Include commands to install and configure each tool.
```

**Deliverable:** Add "Tools and Automation" section to `DOCUMENTATION_STANDARDS.md`

### 7. Add Document Metadata and Introduction

**Write yourself (or use AI):**
- Clear introduction explaining the purpose
- Scope (what docs these standards apply to)
- How to propose changes to the standards
- Version information

**Deliverable:** Add introduction and metadata to `DOCUMENTATION_STANDARDS.md`

## Output Format

Your `DOCUMENTATION_STANDARDS.md` should follow this structure:

```markdown
# TechFlow Documentation Standards

**Version:** 1.0
**Last Updated:** [Date]
**Owner:** Documentation Team

## Introduction

[Purpose of this document, who should follow it, how it helps]

## Scope

These standards apply to:
- All markdown files in this repository
- User-facing documentation
- API documentation
- Internal guides and READMEs

## Quick Reference

[One-page summary of key rules for quick lookup]

---

## 1. Markdown Formatting Standards

### 1.1 Headings
...

### 1.2 Code Blocks
...

[Continue with subsections]

---

## 2. Content Structure Standards

### 2.1 Document Types and Templates
...

### 2.2 File Organization
...

[Continue with subsections]

---

## 3. Quality Requirements

### 3.1 Link Checking
...

### 3.2 Technical Accuracy
...

[Continue with subsections]

---

## 4. Review and Approval Process

### 4.1 Workflow
...

### 4.2 Review Checklist
...

[Continue with subsections]

---

## 5. Style and Voice Guidelines

### 5.1 Tone and Voice
...

### 5.2 Terminology
...

[Continue with subsections]

---

## 6. Tools and Automation

### 6.1 Required Tools
...

### 6.2 Setup Instructions
...

[Continue with subsections]

---

## 7. Document Templates

### 7.1 Tutorial Template
...

### 7.2 API Reference Template
...

[Provide copy-paste templates]

---

## Appendix A: Checklist

Quick checklist for contributors:
- [ ] Formatted according to markdown standards
- [ ] All links checked and working
- [ ] Images have alt text
- [ ] Code examples tested
- [ ] Spelling and grammar checked
- [ ] Reviewed by peer
- [ ] Automated checks passing

---

## Appendix B: Examples

### Good Example
[Show well-formatted, clear documentation]

### Bad Example (Before)
[Show problematic documentation]

### Good Example (After)
[Show the same doc improved]

---

## Proposing Changes to These Standards

[How to suggest improvements to this document]

---

*This document was created with AI assistance as part of documentation quality improvement efforts.*
```

## Success Criteria

You've completed this task when your standards document:

- ✅ Covers all major aspects of documentation quality
- ✅ Provides specific, actionable guidelines
- ✅ Includes examples (both good and bad)
- ✅ Can be enforced through automation where possible
- ✅ Has templates contributors can copy
- ✅ Includes a quick reference checklist
- ✅ Is comprehensive but not overwhelming
- ✅ Reflects the issues found in your audit

## Hints

<details>
<summary>Hint 1: Base Standards on Your Audit</summary>

Review your quality audit. Every issue category should have a corresponding standard to prevent it:
- Found broken links? → Link checking standard
- Found formatting issues? → Markdown formatting standard
- Found outdated content? → Update/review standard
</details>

<details>
<summary>Hint 2: Make It Scannable</summary>

Use:
- Clear section headings
- Numbered or bulleted lists
- Tables for comparisons
- Code examples
- Visual separators

Busy contributors should be able to find what they need quickly.
</details>

<details>
<summary>Hint 3: Balance Thoroughness with Usability</summary>

Aim for "minimum viable standards" that cover 80% of issues with 20% of the complexity. You can always add detail later.
</details>

<details>
<summary>Hint 4: Include Automation</summary>

Wherever possible, suggest tools that can automatically enforce standards:
- Linters for formatting
- Link checkers for broken links
- Spell checkers for typos
- CI/CD for validation

Automation is more reliable than manual checking.
</details>

<details>
<summary>Hint 5: Provide Templates</summary>

Templates lower the barrier to contribution. Include copy-paste templates for:
- Different document types
- Pull request descriptions
- Issue reports
</details>

## Time Management

- **Minutes 0-3:** Create markdown formatting and content structure standards
- **Minutes 4-6:** Define quality requirements and review process
- **Minutes 7-10:** Write style guidelines and tool recommendations
- **Minutes 11-13:** Create templates and checklists
- **Minutes 14-15:** Add introduction, metadata, and polish

## What You've Accomplished

By completing all four tasks in Scenario 1, you have:

- ✅ Systematically explored an unfamiliar repository
- ✅ Identified specific quality issues through AI-assisted auditing
- ✅ Created an executive report communicating findings and priorities
- ✅ Established standards to prevent future issues

These are real-world skills you can apply to any documentation repository!

## What's Next?

Congratulations on completing Scenario 1! You're ready to move to:

**[Scenario 2: The Big Merge](../../scenario-2-big-merge/README.md)**

Where you'll apply these skills to reviewing a complex pull request with multiple file changes.

---

**Need the solution?** Check [solutions/solution-1.4-standards.md](../solutions/solution-1.4-standards.md) when you're ready.
