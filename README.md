# Business Analyst Copilot Workspace

This repository is a minimal VS Code workspace setup for using GitHub Copilot as a **business analyst assistant** while working in tools like **Jira**.

## What is already supported by GitHub Copilot in VS Code

You are **partly right**: recent GitHub Copilot features in VS Code already provide most of the platform capabilities you asked for:

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

## Important limitation

This repository does **not** create a standalone application. Instead, it configures Copilot so you can use the **existing GitHub Copilot + VS Code browser tooling** more effectively for BA work.

## Suggested usage pattern

Use prompts like:

> Act as a business analyst. Review the current Jira issue and surrounding pages, summarize the business need, identify missing functional details, draft a refined user story with acceptance criteria, and stop for approval before making any Jira changes.

## Review and approval model

The included instructions are designed so that Copilot should:

- explain its plan first
- draft Jira content before applying it
- ask for approval before making browser actions that change data
- keep edits traceable and easy to review

That means the answer to your original question is:

- **Yes**: Copilot in VS Code already provides the core browser and approval capabilities
- **No, not completely by default**: it still benefits from repository instructions and reusable prompts to behave like a BA working in Jira