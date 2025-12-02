# Effective AI Prompts for Repository Management

This guide contains proven AI prompts for common repository management tasks. These prompts work well with GitHub Copilot, Claude, ChatGPT, and similar AI assistants.

## Table of Contents

1. [Repository Exploration](#repository-exploration)
2. [Content Auditing](#content-auditing)
3. [PR Review](#pr-review)
4. [Issue Management](#issue-management)
5. [Documentation Writing](#documentation-writing)
6. [Quality Checks](#quality-checks)

---

## Repository Exploration

### Understanding Repository Structure

```
Analyze this repository structure and help me understand it:

[Paste directory tree or file listing]

Please provide:
1. A summary of what this repository contains
2. The purpose of each major directory
3. How the content is organized
4. Any patterns or conventions you notice
5. What type of project this appears to be
```

### Mapping Content by Topic

```
I have these documentation files:

[List files with brief descriptions or first paragraphs]

Please categorize them by:
- Content type (tutorial, guide, reference, API docs, etc.)
- Topic area
- Intended audience
- Completeness status

Present as a table or structured list.
```

### Identifying Documentation Gaps

```
This repository contains the following documentation:

[List current documentation]

For a [type of project, e.g., "workflow automation platform"], what essential documentation is missing?

Consider:
- Getting started guides
- Installation instructions
- API references
- Troubleshooting guides
- Contributing guidelines
- Architecture documentation
```

---

## Content Auditing

### Finding Broken Links

```
Review these markdown files for broken links:

[Share file contents or sections]

Identify:
1. Internal links that might be broken (file paths, anchors)
2. External URLs that look outdated or suspicious
3. Link formatting issues
4. Missing link text

For each issue, specify the file and line number.
```

### Checking for Outdated Content

```
Analyze this documentation for outdated content:

[Share documentation sections]

Look for:
1. Old version numbers (e.g., "Python 2.7", "Node 10")
2. Deprecated features or APIs
3. References to old tools or services
4. Screenshots that mention old UI
5. "Last updated" dates more than [X] months old

Be specific about what's outdated and what it should be updated to.
```

### Formatting Consistency Check

```
Compare the formatting across these markdown files:

[Share multiple files]

Check for inconsistencies in:
1. Heading levels and capitalization
2. Code block formatting (language specifiers)
3. List formatting (bullets, numbers, indentation)
4. Table structures
5. Link formatting (inline vs reference style)
6. Bold/italic usage

List specific examples of inconsistencies with file and line numbers.
```

---

## PR Review

### High-Level PR Analysis

```
Review this pull request:

**PR Title:** [Title]
**Description:** [Description]
**Files Changed:** [List with +/- counts]

Provide:
1. Summary of what this PR accomplishes
2. Change categorization (new features, updates, fixes, refactoring)
3. Potential risks or concerns
4. Areas that need careful review
5. Whether the scope is appropriate
```

### Detailed Content Review

```
Compare the before and after versions of this file:

**Before:**
[Original content]

**After:**
[Changed content]

Analyze:
1. What changed and why
2. Technical accuracy of changes
3. Style and formatting consistency
4. Completeness of the update
5. Any concerns or issues
6. Suggested improvements

Be specific and provide examples.
```

### Cross-Reference Validation

```
This PR modifies/deletes these files:

[List changed/deleted files]

Check for:
1. Links in other files that might now be broken
2. Table of contents or navigation that needs updating
3. Related documentation that should also be updated
4. References to the old content that need changing

Identify specific files that might need attention.
```

### Generating PR Feedback

```
Based on these review findings:

[Paste your review notes]

Draft a PR review comment that:
1. Starts with positive feedback on what's done well
2. Groups issues by category (critical, important, minor)
3. Provides specific, actionable suggestions
4. Includes example fixes where helpful
5. Ends with clear next steps
6. Maintains a constructive, helpful tone

The audience is a contributor who put significant effort into this PR.
```

---

## Issue Management

### Bulk Issue Categorization

```
Categorize these issues:

Issue #1: [Title and description]
Issue #2: [Title and description]
Issue #3: [Title and description]
[Continue...]

For each issue, provide:
- Type: (bug, feature, question, discussion, typo)
- Priority: (critical, high, medium, low)
- Effort: (quick-win <1hr, medium 1-4hrs, large >4hrs)
- Status: (actionable, needs-info, duplicate, wont-fix)

Present as a table.
```

### Finding Duplicate Issues

```
Review these issues and identify duplicates or closely related items:

[List issues with descriptions]

Identify:
1. Exact duplicates (same issue, different words)
2. Closely related issues (should be handled together)
3. Conflicting requests (mutually exclusive)
4. Dependencies (one blocks another)

For each relationship, explain why they're connected.
```

### Drafting Issue Responses

```
Draft a response to this issue:

**Issue #[N]:** [Title]
**Description:** [Issue description]
**Context:** [Any relevant context]

The response should:
1. Acknowledge the issue clearly
2. [Explain why it's valid / Ask for more information / Explain why we won't fix]
3. [If valid: Describe next steps / If needs info: Ask specific questions / If wont-fix: Suggest alternatives]
4. Be professional, friendly, and helpful
5. Be concise (2-4 paragraphs)

The tone should be [helpful/apologetic/explanatory] depending on the situation.
```

---

## Documentation Writing

### Improving Clarity

```
Improve the clarity of this documentation:

[Paste documentation section]

Make it:
1. Easier to understand for [target audience]
2. More concise without losing important information
3. Better structured with clear headings
4. Include examples where helpful
5. Use active voice
6. Define jargon and technical terms

Show before and after versions.
```

### Writing Step-by-Step Instructions

```
Convert this process description into clear step-by-step instructions:

[Paste description]

Format as:
1. Clear prerequisites (what users need before starting)
2. Numbered steps with one action each
3. Expected outcomes for each step
4. Troubleshooting tips for common issues
5. Success criteria (how to know it worked)

Target audience: [describe audience level]
```

### Creating Examples

```
Create a code example for this documentation:

**Concept:** [What needs to be demonstrated]
**Language:** [Programming language]
**Complexity:** [Simple/Medium/Complex]
**Context:** [Where it fits in the docs]

The example should:
1. Be realistic and practical
2. Include comments explaining key parts
3. Show best practices
4. Be copy-paste ready
5. Include expected output if applicable
```

---

## Quality Checks

### Accessibility Review

```
Review this documentation for accessibility:

[Share content]

Check for:
1. Images without alt text or descriptions
2. Non-descriptive link text ("click here", "here")
3. Poor heading hierarchy
4. Jargon without explanation
5. Overly complex sentences
6. Missing context or prerequisites

Suggest specific improvements.
```

### Comprehensive Quality Audit

```
Perform a quality audit on this documentation:

[Share file or section]

Evaluate on:
1. **Accuracy:** Is the information correct and current?
2. **Completeness:** Are there gaps or missing information?
3. **Clarity:** Is it easy to understand?
4. **Organization:** Is it well-structured?
5. **Examples:** Are there sufficient examples?
6. **Consistency:** Does it match the style of other docs?
7. **Accessibility:** Can all users access the information?

Provide a score (1-10) for each dimension and specific improvement suggestions.
```

### Technical Accuracy Validation

```
Validate the technical accuracy of this documentation:

[Share technical content]

Check:
1. Code examples (syntax, best practices, deprecations)
2. Command-line instructions (will they work?)
3. API endpoints and parameters
4. Configuration examples
5. System requirements
6. Version numbers

Flag anything that might be incorrect or outdated, explaining why.
```

---

## Best Practices for AI-Assisted Repository Management

### 1. Be Specific in Your Prompts

❌ Bad: "Review this documentation"
✅ Good: "Review this API documentation for technical accuracy, focusing on endpoint descriptions and example code"

### 2. Provide Context

Include:
- What type of project this is
- Who the target audience is
- What you're trying to accomplish
- Any specific concerns or focus areas

### 3. Ask for Structured Output

Request:
- Tables for easy scanning
- Bullet points for clarity
- Examples with explanations
- Specific file and line numbers

### 4. Iterate and Refine

Start broad, then narrow:
1. "Summarize these changes"
2. "Focus on the API reference changes"
3. "Check the code examples in the API reference for accuracy"

### 5. Validate AI Suggestions

AI is powerful but not perfect:
- Spot-check important findings
- Verify technical claims
- Confirm link checks
- Test suggested code examples

### 6. Batch Similar Tasks

Process similar items together:
- Review all new files at once
- Check all external links together
- Categorize all issues in one prompt

### 7. Save and Reuse Effective Prompts

When you find a prompt that works well:
- Save it
- Refine it
- Create templates
- Share with your team

---

## Prompt Templates by Task

### Quick Repository Overview
```
Analyze [repository/directory] and provide:
1. What it contains (2-3 sentences)
2. Main sections/categories
3. Target audience
4. Key strengths and gaps
```

### Quality Issue Finder
```
Review [file/section] for quality issues:
- Broken links
- Outdated content
- Formatting problems
- Missing information
- Technical inaccuracies

List specific issues with locations.
```

### PR Review Template
```
Review this PR:
Files: [list]
Purpose: [description]

Provide:
1. Overall assessment
2. Issues by priority (critical/high/medium/low)
3. Specific suggestions with examples
4. Recommendation (approve/request changes/reject)
```

### Issue Triage Template
```
Categorize these issues:
[issue list]

For each:
- Type: bug/feature/question/other
- Priority: critical/high/medium/low
- Effort: small/medium/large
- Action: fix/needs-info/duplicate/wont-fix
```

---

## Advanced Techniques

### Chain of Thought Prompting

Ask AI to explain its reasoning:

```
Review this documentation and explain your thought process:

1. First, identify what type of documentation this is
2. Then, determine the target audience
3. Next, check for common issues
4. Finally, prioritize findings by impact

[Share content]

Walk me through your analysis step by step.
```

### Comparative Analysis

Compare different approaches:

```
Compare these two versions of the same documentation:

Version A: [content]
Version B: [content]

Which is better for [specific audience/goal] and why?
Consider: clarity, completeness, examples, structure, tone.
```

### Root Cause Analysis

Understand patterns:

```
I found these issues in the repository:

[List issues]

What patterns do you see? What might be the root causes?
What systemic changes would prevent these issues?
```

---

## Tips for Working with AI Assistants

1. **Start conversations with context**: "I'm reviewing documentation for a workflow automation platform..."

2. **Use follow-up prompts**: AI remembers context within a conversation - build on previous responses

3. **Ask for alternatives**: "Give me 3 different ways to phrase this"

4. **Request explanations**: "Why did you categorize this as high priority?"

5. **Specify format preferences**: "Format as a markdown table" or "Use bullet points"

6. **Set constraints**: "Keep responses under 200 words" or "Focus only on critical issues"

7. **Request examples**: "Show me an example of what you mean"

8. **Iterate**: If the first response isn't quite right, refine your prompt

---

**Remember:** AI is a powerful tool for repository management, but human judgment is essential. Use AI to work faster and more thoroughly, but always validate important findings and decisions.
