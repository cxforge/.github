# Plans & Tasks

This folder contains task instructions, implementation plans, and project roadmaps.

## Purpose

The `.plans/` folder houses:
- Implementation plans for features
- Migration strategies
- Refactoring roadmaps
- Deployment plans
- Research tasks and experiments

## Organization

```
.plans/
├── README.md           # This file
├── active/             # Currently in-progress plans
├── backlog/            # Future ideas and tasks
└── templates/          # Plan templates
```

## Plan File Structure

Each plan should include:
- **Goal:** What we're trying to achieve
- **Context:** Background and rationale
  - Include links/paths to relevant `.specs/` documents
  - Reference `.agents/` context files if AI-specific knowledge is needed
  - Link to main `README.md` for high-level overview
- **Approach:** How we'll do it
- **Tasks:** Specific steps with checkboxes
  - Each task should point to all required context (`.specs/`, `.agents/`, `README.md`)
  - Tasks must be written so a cloud agent (Jules, Cursor Cloud, etc.) can complete them autonomously
- **Risks:** What could go wrong
- **Dependencies:** What we need first
  - Link to blocking `.specs/` or other `.plans/` as needed

## When to Update

- New features are planned
- Current work needs documentation
- Tasks are completed
- Plans change scope or approach

## Guidelines

- Keep plans focused and achievable — if a plan cannot be completed in one concise implementation, break it into multiple smaller plans
- Update status regularly
- Link to related `.specs/` documents
- **Delete completed plans** — don't keep them; if the plan is too large to complete, it should have been broken into smaller task plans
- **Human review consideration:** Changes should be made in easily reviewable sizes that won't be blocked by long, slow reviews
