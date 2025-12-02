# Task 1.1: Repository Exploration with GitHub Copilot

**Duration:** 15 minutes
**Difficulty:** Beginner
**GitHub Copilot Features:** @workspace agent, Copilot Chat

## Objective

Quickly understand the structure, organization, and purpose of the TechFlow documentation repository using GitHub Copilot's @workspace agent and context awareness.

## Context

You've just inherited an unfamiliar repository. Before diving into fixes, you need to understand what you're working with. Manual exploration would take hours - GitHub Copilot's @workspace agent can analyze the entire repository and help you understand the landscape in minutes.

## Your Challenge

Create a comprehensive repository map using GitHub Copilot's workspace understanding to answer key questions about the content, structure, and purpose of this documentation.

## Setup

1. **Open the challenge repository in VS Code:**
   ```bash
   cd scenario-1-inheritance/challenge-repo
   code .
   ```

2. **Open Copilot Chat:**
   - Press `Ctrl+Shift+I` (Windows/Linux) or `Cmd+Shift+I` (Mac)
   - Or click the Copilot icon in the sidebar

3. **Verify @workspace is available:**
   - Type `@workspace` in the chat - you should see it autocomplete
   - This gives Copilot context about your entire repository

## Tasks

### 1. Generate Repository Structure Overview with @workspace

**Use GitHub Copilot Chat with @workspace:**

Open Copilot Chat and use this prompt:

```
@workspace Analyze this repository structure and provide:
1. A tree diagram showing the main directories and key files
2. The purpose of each directory
3. The types of content in each section (markdown, Python, etc.)
4. Overall organization pattern (by topic, by type, by audience?)
5. What type of project this appears to be

Format as markdown for easy copying.
```

**Why @workspace?** The @workspace agent gives Copilot context about your entire repository structure, file contents, and relationships - providing much richer analysis than looking at individual files.

**Expected Output:** Copilot will analyze the entire workspace and provide:
- Complete directory structure
- Purpose of each section
- File type distribution
- Organizational insights

**Deliverable:**
1. Create a new file: `repository-map.md`
2. Copy Copilot's response as your first section
3. Clean up formatting if needed

---

### 2. Identify Content Categories

**Copilot Chat Prompt:**

```
@workspace Categorize all markdown files in this repository by:
- Content type (tutorial, guide, reference, API docs, etc.)
- Topic area (getting started, advanced features, API, troubleshooting, etc.)
- Intended audience (beginners, developers, administrators)
- Completeness (complete, in-progress, has TODOs)

Present as a table with columns: File, Type, Topic, Audience, Status
```

**What Copilot Does:**
- Reads all markdown files in the workspace
- Analyzes headers, structure, and content
- Identifies patterns and categories
- Generates a comprehensive table

**Pro Tip:** If the table is too long, ask Copilot to summarize:
```
@workspace Summarize the categorization - how many of each type, what's the overall distribution?
```

**Deliverable:** Add the "Content Categories" section to your `repository-map.md`

---

### 3. Analyze Python Utilities

**Copilot Chat Prompt:**

```
@workspace I see Python files in the utils/ directory. For each script:
1. What does it do?
2. When would you use it?
3. What are its dependencies?
4. Is it well-documented?
5. Could it help with documentation quality checks?

Provide a summary for each script.
```

**What Copilot Does:**
- Analyzes Python code in utils/
- Reads docstrings and comments
- Identifies imports and dependencies
- Assesses code quality and documentation
- Suggests use cases

**Follow-up Prompt (if needed):**
```
@workspace Can you show me how to run the link_checker.py script? What command would I use?
```

**Deliverable:** Add "Utility Scripts Analysis" section to `repository-map.md`

---

### 4. Identify Documentation Gaps

**Copilot Chat Prompt:**

```
@workspace Based on the documentation files present, what essential documentation is missing for a complete documentation set?

Consider:
- Getting started guides
- Contributing guidelines
- Architecture documentation
- Troubleshooting guides
- FAQ
- Code of conduct
- License
- Changelog

What's here and what's missing?
```

**What Copilot Does:**
- Compares existing files against documentation best practices
- Identifies missing essential documents
- Suggests what should be added
- Prioritizes by importance

**Deliverable:** Add "Documentation Gaps" section to `repository-map.md`

---

### 5. Create Visual Repository Map

**Copilot Chat Prompt:**

```
@workspace Create a visual map of this documentation repository using Mermaid diagram syntax showing:
1. The main documentation sections as nodes
2. How they relate to each other (arrows)
3. The typical user journey through the docs
4. Entry points for different user types (beginner, advanced, API user)

Use this structure:
```mermaid
graph TD
    Start[New User Arrives]
    ...
```

**What Copilot Does:**
- Generates Mermaid diagram syntax
- Shows information architecture
- Maps user journeys
- Identifies relationships between sections

**To Render the Diagram:**
1. Copy the Mermaid code
2. Paste into your `repository-map.md`
3. VS Code with Markdown preview will render it automatically
4. Or use https://mermaid.live to see it

**Deliverable:** Add "Visual Repository Map" section with Mermaid diagram

---

### 6. Generate Key Findings Summary

**Copilot Chat Prompt:**

```
@workspace Based on our analysis of this repository, provide:
1. Top 3 strengths (what's well done)
2. Top 3 issues or gaps (what needs work)
3. Recommended next steps (prioritized)
4. Overall assessment (1-2 sentences)

Be specific with file names and examples.
```

**What Copilot Does:**
- Synthesizes all previous analysis
- Identifies patterns and priorities
- Provides actionable recommendations
- Gives you talking points for stakeholders

**Deliverable:** Add "Key Findings & Recommendations" section to `repository-map.md`

---

## GitHub Copilot Tips for This Task

### Using @workspace Effectively

✅ **Do:**
- Start prompts with `@workspace` for repository-wide analysis
- Ask follow-up questions to drill deeper
- Request specific formats (tables, lists, diagrams)
- Ask for examples and file references

❌ **Don't:**
- Try to manually read every file (let Copilot do it)
- Forget to use `@workspace` (limits context)
- Accept first response without asking for clarification
- Skip validation (spot-check Copilot's findings)

### Keyboard Shortcuts

- `Ctrl+Shift+I` / `Cmd+Shift+I` - Open Copilot Chat
- `Ctrl+I` / `Cmd+I` - Inline Copilot (for quick edits)
- `Alt+\` - Trigger inline suggestion
- `Tab` - Accept suggestion

### If Copilot's Response is Too Long

Ask it to summarize:
```
Can you provide a shorter version focusing on the most important points?
```

Or ask for specific sections:
```
Let's focus on just the markdown files for now. Analyze those first.
```

---

## Output Format

Your `repository-map.md` should include these sections created with Copilot:

```markdown
# TechFlow Documentation Repository Map

**Generated with:** GitHub Copilot @workspace
**Date:** [Date]

## Executive Summary
[2-3 sentences from Copilot describing what this repository contains]

## Repository Structure
[Copilot-generated tree diagram and explanation]

## Content Categories
[Copilot-generated table of all markdown files]

### Summary Statistics
- Total markdown files: X
- By type: Y tutorials, Z guides, etc.
- By status: A complete, B in-progress

## Utility Scripts Analysis
[Copilot analysis of Python scripts]

### link_checker.py
- Purpose: [Copilot's explanation]
- Usage: [Command to run]
- Dependencies: [What it needs]

### format_validator.py
- Purpose: [Copilot's explanation]
...

## Documentation Gaps
[Copilot's list of missing essential docs]

Priority gaps:
1. [Missing item 1]
2. [Missing item 2]
...

## Visual Repository Map
[Copilot-generated Mermaid diagram]

## Key Findings
[Copilot's analysis]

### Strengths
1. [Strength 1]
2. [Strength 2]
3. [Strength 3]

### Issues/Gaps
1. [Issue 1]
2. [Issue 2]
3. [Issue 3]

### Recommended Next Steps
1. [Action 1]
2. [Action 2]
3. [Action 3]

## Overall Assessment
[Copilot's 1-2 sentence summary]
```

---

## Success Criteria

You've completed this task when you can:

- ✅ Explain the repository structure to someone who's never seen it
- ✅ List all major content categories with file counts
- ✅ Describe what the Python utilities do and how to use them
- ✅ Identify 5+ significant documentation gaps
- ✅ Provide a visual map showing information architecture
- ✅ Make informed recommendations about priorities

---

## Advanced: Going Deeper with Copilot

Once you have the basics, try these advanced prompts:

**Analyze Content Quality:**
```
@workspace Which documentation files have the most outdated information? Look for old dates, deprecated features, or version references.
```

**Find Related Files:**
```
@workspace If I wanted to update the API documentation, which other files would likely need updates too?
```

**Suggest Improvements:**
```
@workspace Based on the existing structure, suggest a better way to organize these docs for new users.
```

---

## Hints

<details>
<summary>Hint 1: @workspace is Your Friend</summary>

Always use `@workspace` at the start of your prompts for repository-wide analysis. Without it, Copilot only knows about the currently open file.

Compare:
- ❌ "Analyze this repository" (limited context)
- ✅ "@workspace Analyze this repository" (full context)
</details>

<details>
<summary>Hint 2: Iterative Questions</summary>

Don't try to get everything in one prompt. Have a conversation:
1. "@workspace Give me an overview"
2. "Tell me more about the Python utilities"
3. "What's in the docs/ directory specifically?"

Each response builds context.
</details>

<details>
<summary>Hint 3: Request Specific Formats</summary>

Tell Copilot how you want the output:
- "as a markdown table"
- "as a bullet list"
- "as a Mermaid diagram"
- "as a tree structure"

This makes responses more useful.
</details>

<details>
<summary>Hint 4: Validate Findings</summary>

Copilot is powerful but not perfect. Spot-check:
- Do the files it mentions actually exist?
- Are the descriptions accurate?
- Does the analysis make sense?

Trust but verify.
</details>

---

## Time Management

- **Minutes 0-3:** Set up workspace, open Copilot Chat
- **Minutes 4-7:** Repository structure and content categories
- **Minutes 8-10:** Python utilities analysis
- **Minutes 11-13:** Documentation gaps and visual map
- **Minutes 14-15:** Key findings and create final document

---

## What's Next?

After completing your repository map, you'll move to **Task 1.2** where you'll use GitHub Copilot to conduct a detailed content quality audit, finding specific issues like broken links and outdated information.

---

## Troubleshooting

**Problem:** @workspace not available
**Solution:** Make sure you have:
- GitHub Copilot extension installed and activated
- Opened the folder in VS Code (not just individual files)
- Latest version of VS Code

**Problem:** Copilot's responses are too generic
**Solution:** Be more specific in your prompts:
- Reference specific directories
- Ask for file names
- Request examples
- Ask follow-up questions

**Problem:** Copilot missed something
**Solution:** Ask directly:
- "@workspace I see a utils/ directory. What's in there?"
- "@workspace Are there any Python files?"

---

**Need the solution?** Check [solutions/solution-1.1-explore.md](../solutions/solution-1.1-explore.md) for example Copilot interactions and outputs.
