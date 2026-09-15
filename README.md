# Business Analyst Copilot Workspace

This repository is a minimal VS Code workspace setup for using GitHub Copilot as a **business analyst assistant** while working in tools like **Jira**.

## What is already supported by GitHub Copilot in VS Code

Recent GitHub Copilot features in VS Code already provide most of the platform capabilities needed for this workflow:

- **Browser interaction** so the agent can open a page, click, type, and read UI state in a shared browser session
- **Repository custom instructions** so the agent can follow a BA-style workflow in this repository
- **Approval-oriented workflows** such as reviewing a plan first and confirming sensitive actions before they run

What Copilot does **not** know by default is **how you want it to behave as a business analyst** in Jira. This repository adds that missing part.

## What this repository adds

- `.github/copilot-instructions.md`  
  Repository-wide instructions telling Copilot to act like a pragmatic business analyst consultant
- `.github/prompts/jira-business-analyst.prompt.md`  
  A reusable prompt for Jira-oriented BA work in VS Code

## Expected workflow

1. Open this repository in **VS Code**
2. Open **Copilot Chat / Agent mode**
3. Open the target website you want to work with and share it with the agent when needed
4. Start from the reusable prompt in `.github/prompts/jira-business-analyst.prompt.md`
5. Let the agent:
   - analyze the current process or feature
   - draft requirements, user stories, and acceptance criteria
   - propose UAT or functional test ideas
   - suggest documentation updates
6. Review the draft before approving any state-changing action such as:
   - creating or editing Jira tickets
   - changing issue fields
   - submitting comments

## Step-by-step guide

Use this flow for day-to-day Jira support in VS Code:

1. Open your local clone of this repository in **VS Code**
2. Open **Copilot Chat** and switch to an agent-based workflow if available
3. Open the Jira page, ticket, or other business tool page you want to work on
4. Share the browser/page context with Copilot so it can read the current screen
5. Start with the prompt in `.github/prompts/jira-business-analyst.prompt.md` or ask Copilot to:
   - summarize the business objective
   - identify gaps, risks, and assumptions
   - draft a user story or business requirement
   - prepare acceptance criteria and UAT notes
6. Review Copilot's draft carefully
7. Ask for refinements until the wording, scope, and acceptance criteria are correct
8. Only after review, explicitly approve the change you want Copilot to make in Jira
9. Let Copilot apply the approved update
10. Review the final result and confirm that the Jira content matches the approved draft

### Example review-first workflow

Use prompts like:

> Review this Jira issue as a business analyst. First summarize what you see, then draft an improved user story with acceptance criteria and open questions. Do not make any Jira changes until I approve the draft.

After reviewing the draft, approve the exact next step with prompts like:

> Approved. Update the Jira description with the drafted business context, user story, and acceptance criteria only.

## Important limitation

This repository does **not** create a standalone application or change Copilot itself. Instead, it provides guidance files that help you use the **existing GitHub Copilot + VS Code browser tooling** more effectively for BA work.

## Suggested usage pattern

Use prompts like:

> Act as a business analyst. Review the current Jira issue and surrounding pages, summarize the business need, identify missing functional details, draft a refined user story with acceptance criteria, and stop for approval before making any Jira changes.

## Review and approval model

The included instructions are designed so that Copilot should:

- explain its plan first
- draft Jira content before applying it
- ask for approval before making browser actions that change data
- keep edits traceable and easy to review

In practice, this means:

- GitHub Copilot in VS Code already provides the core browser and approval capabilities
- Repository instructions and reusable prompts help shape that capability into a consistent BA workflow for Jira