# AI Agent Instructions

This folder contains AI assistant (Cursor, Copilot, etc.) specific instructions and context for this repository.

## Purpose

The `.agents/` folder houses:
- Repository-specific AI assistant rules
- Context about codebase structure
- Decision rationales that help AI assistants understand "why"
- Known issues and workarounds
- Common patterns to follow/avoid

## Organization

```
.agents/
├── README.md           # This file
├── context.md          # High-level codebase context
├── patterns.md         # Common patterns and anti-patterns
├── decisions.md        # Key decisions AI should know about
└── troubleshooting.md  # Known issues and solutions
```

## When to Update

- AI assistants make consistent mistakes
- Codebase structure changes significantly
- New patterns emerge
- New types of tasks are automated

## Guidelines

- Be specific about what AI should/shouldn't do
- Reference actual files and patterns
- Keep security considerations in mind
- Update when AI behavior needs correction
