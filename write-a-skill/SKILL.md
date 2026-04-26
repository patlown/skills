---
name: write-a-skill
description: Create a new well-structured Claude Code skill from scratch. Use when user wants to write, create, or scaffold a new skill.
---

# Writing a Skill

When asked to create a new skill, follow this process:

## 1. Understand the intent

Ask the user what the skill should do, when it should trigger, and what the expected output looks like. Clarify scope before writing.

## 2. Create the skill directory

```
skill-name/
├── SKILL.md           # Main instructions (required)
├── REFERENCE.md       # Detailed docs (if needed)
├── EXAMPLES.md        # Usage examples (if needed)
└── scripts/           # Utility scripts (if needed)
    └── helper.sh
```

- Directory name: kebab-case, matches the `name` field in frontmatter
- Every skill needs exactly one `SKILL.md`

## 3. Write the SKILL.md

### Frontmatter (required)

```yaml
---
name: skill-name
description: What it does in one sentence. Use when [trigger conditions].
---
```

- `name`: kebab-case, matches the directory name
- `description`: Max 1024 characters. First sentence = what it does. Second sentence = when to use it. This is the only thing the agent sees when deciding whether to load the skill, so make it count.

### Body

Write clear, imperative instructions. The body is what the agent follows when the skill is invoked.

**Guidelines:**
- Lead with the goal, then the steps
- Use numbered steps for sequential workflows
- Use bullet points for rules and constraints
- Be specific — vague instructions produce vague results
- Keep it under 100 lines if possible; split into supplementary files if longer
- Reference supplementary files with relative links: `See [REFERENCE.md](REFERENCE.md)`

## 4. Supplementary files

Use these when:
- SKILL.md would exceed ~100 lines
- Content has distinct domains (e.g., separate docs for testing vs. architecture)
- Reference material is only needed occasionally

Naming conventions:
- UPPER-CASE for primary references: `REFERENCE.md`, `EXAMPLES.md`
- lower-case for topical references: `mocking.md`, `tests.md`

## 5. Scripts

Use a `scripts/` subdirectory for deterministic operations where generating code each time would waste tokens or risk inconsistency (e.g., validation, formatting, git hooks).

## 6. Update the README

After creating the skill, add it to the table in `README.md`.
