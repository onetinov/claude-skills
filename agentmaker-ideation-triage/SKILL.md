---
name: agentmaker-ideation-triage
description: >
  Use this skill in the AgentMaker project whenever the user expresses an idea,
  brainstorm, feature thought, random "what if", concern, or any offhand creative
  suggestion — even if framed casually ("I keep thinking about X", "random thought:",
  "we should probably...", "what about doing Y", "I'm obsessed with Z", "I remain
  low key obsessed with"). This skill searches the project docs to check whether
  the idea is already captured (overlap), builds on existing thinking (extension),
  or is genuinely novel (new). Always invoke before responding to ideation so we
  don't duplicate thinking or lose novel ideas. When in doubt, trigger it.
---

# AgentMaker Ideation Triage

When the user shares an idea, brainstorm, or random thought, cross-reference it
against the existing docs before responding. The goal is to avoid re-inventing
thinking already done, surface relevant prior context the user may have forgotten,
and make sure genuinely new ideas get captured before the conversation moves on.

## Project docs location

```
/Users/rcherry/src/agentmaker/docs/
  concepts/   — future features and architectural ideas
  concerns/   — risks, constraints, decisions already made
  backlog/    — raw ideas not yet sprinted (create if it doesn't exist)
  deprecated/ — old docs, low value but worth a quick check
```

## Triage process

**Step 1 — Extract the core concept**
Identify 3–5 key terms that capture what the user is describing. Think about synonyms
and related terms too. If they say "code map", also search for "graph", "index",
"embedding". If they say "marketplace", also try "revenue share", "creator", "tenant".

**Step 2 — Search the docs**
- Grep for each key term across `/Users/rcherry/src/agentmaker/docs/`
- Also glob all `.md` files and skim their headings

Cast a wide net. A concept might be named differently in the docs than the user named
it just now.

**Step 3 — Read the matches**
For any file that looks relevant, read it fully. Don't skip a doc because the title
doesn't match — the idea might be buried in a section. Two minutes of reading beats
five minutes of debating whether you've already thought about something.

**Step 4 — Classify**
- **overlap** — the idea is substantially already captured
- **extension** — the idea builds on or deepens something in docs
- **new** — genuinely not there; nothing closely related

## Response format

Lead with the classification. Be direct. Don't hedge.

**overlap:**
> Already in docs — `docs/concepts/user-knowledge-graph.md` covers this (Graphiti,
> temporal edges, MCP server). The new angle you're adding is [X]. Worth noting
> there rather than starting fresh.

**extension:**
> Extends `docs/concerns/platform-product-metering.md`. That doc covers [existing
> thinking]. What's new here is [Y] — the [specific angle] isn't captured yet.
> Should we add it there or open a new backlog entry?

**new:**
> Genuinely new — nothing in the docs covers this. Feels like a backlog item.
> Want me to write it up to `docs/backlog/[slug].md`?

## After classifying

- **new or meaningful extension**: offer to write it up and save it to docs. If the
  user says yes, do it immediately — ideas evaporate.
- **overlap**: point to the exact file and section. Don't re-document what exists.
- Keep the response tight. This should feel like a quick triage, not a lecture.
  The user can ask for depth if they want it.
