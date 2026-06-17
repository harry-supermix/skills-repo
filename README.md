# Skills

A curated, growing collection of my favorite [Claude](https://claude.com) skills.

Skills are self-contained folders that teach Claude how to do something well — each is a `SKILL.md` file with YAML frontmatter (`name` + `description`) and a body of instructions. Claude reads the description to decide when a skill applies, then loads the body for guidance. They work with [Claude Code](https://docs.claude.com/en/docs/claude-code), the Claude apps, and the Agent SDK.

This repo is hand-picked and updated over time — not an exhaustive index. Things land here once they've earned their place.

## Skills

| Skill | What it's for |
|-------|---------------|
| [`frontend-design`](frontend-design/SKILL.md) | Distinctive, intentional visual design when building or reshaping UI — aesthetic direction, typography, and choices that don't read as templated defaults. |
| [`luck`](luck/SKILL.md) | A decision-making framework grounded in Assembly Theory for increasing the likelihood of fortunate outcomes — for ambiguous choices, experiments, strategy, and building things meant to persist. |

## Using a skill

**Claude Code** — copy a skill folder into one of the directories Claude Code scans for skills:

```bash
# Personal skills, available across all your projects
mkdir -p ~/.claude/skills
cp -r frontend-design ~/.claude/skills/

# Or scoped to a single project, checked in with the repo
mkdir -p .claude/skills
cp -r luck .claude/skills/
```

Restart Claude Code (or start a new session) and it will pick the skill up automatically when a request matches its description. You can also invoke one explicitly with `/frontend-design`.

**Claude apps** — upload a skill via the Capabilities settings, or zip the folder and add it as a custom skill where supported.

## Anatomy of a skill

```
skill-name/
└── SKILL.md          # required: frontmatter + instructions
    ├── supporting files (optional): scripts, templates, reference docs
```

The frontmatter is what makes a skill discoverable:

```yaml
---
name: skill-name
description: One or two sentences on what this does and, crucially, when to use it.
---
```

A sharp `description` matters most — it's the only thing Claude sees when deciding whether a skill is relevant, so it should name the triggers ("use when…") as much as the capability.

## Contributing

This is a personal collection, but suggestions are welcome — open an issue with a skill worth adding.
