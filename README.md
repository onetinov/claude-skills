# claude-skills

Personal Claude Code skills. Install by copying any skill directory to `~/.claude/skills/` — Claude Code picks them up automatically on next session.

## Skills

### `agentmaker-ideation-triage`

Detects when you're brainstorming or expressing an idea in the AgentMaker project and searches the project docs before responding. Classifies the idea as:

- **overlap** — already captured in docs, points to the exact file
- **extension** — builds on existing thinking, identifies what's new
- **new** — genuinely novel, offers to write it up immediately

Triggers on phrases like "I keep thinking about...", "random thought:", "what if we...", "I'm obsessed with...", "we should probably..."

**Install:**
```bash
cp -r agentmaker-ideation-triage ~/.claude/skills/
```

**Note:** The docs path is hardcoded to `/Users/rcherry/src/agentmaker/docs/`. Fork and update `SKILL.md` for your own project path.
