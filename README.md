# claude-skills

Personal Claude Code skills. Install any skill by copying its directory to `~/.claude/skills/` — Claude Code picks it up automatically on next session.

## Skills

### `thinking-partner`

A two-phase skill that first checks whether your idea already exists in project docs, then acts as a structured thinking partner to develop and pressure-test it.

**Phase 1 — Ideation Triage:** Discovers project documentation, searches for related concepts, and classifies the idea as:
- **overlap** — already captured, points to the exact file
- **extension** — builds on existing thinking, identifies what's new
- **new** — genuinely novel, offers to write it up immediately

**Phase 2 — Thinking Framework:** Develops the idea through five stages:
1. **Clarify** — forces articulation of the actual claim
2. **Stress-Test** — finds weaknesses before the audience does
3. **Reconstruct** — rebuilds the idea stronger
4. **Structure** — produces a detailed outline to build from
5. **Refine** — targeted critique of the draft

Triggers on phrases like "I keep thinking about...", "random thought:", "what if we...", "I'm obsessed with...", "help me think through...", "I have this idea for..."

**Install:**
```bash
cp -r thinking-partner ~/.claude/skills/
```

Works with any project — dynamically discovers docs in `docs/`, `README.md`, `ARCHITECTURE.md`, and other common locations.
