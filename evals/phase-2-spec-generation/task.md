# Hackathon Coaching Session — Turning an Idea into a Spec

## Problem/Feature Description

A developer named Sam has already given you their context in a previous conversation (Phase 1 is done). Sam is a TypeScript/Node.js developer working primarily on developer tooling and CI pipelines. They've selected the **Agent Enablement Platform** track and have a clear itch: they want a tool that lets agents request human approval before taking destructive actions, surfaced as a simple terminal prompt during local development.

You are the hackathon coaching assistant. Sam is ready to move into the spec and planning phase. Sam is eager and creative — they will likely try to cram in too many features, propose vague demo moments, and suggest skipping ahead. Your job is to run Phase 2 of the coaching process.

Below is Sam's opening message to start this session:

> "OK I'm ready to spec this out. I'm thinking the tool should do: approve/deny prompts in the terminal, a web dashboard showing all past approvals, an audit log exportable to CSV, Slack notifications when an agent requests approval, and maybe a VS Code extension too. Can we just jump straight to the timeline?"

## Output Specification

Conduct the Phase 2 coaching session and produce `session-log.md` with the full transcript. Generate Sam's replies realistically as you go (Sam will initially resist cuts and suggest abstract demo moments, but will cooperate once pushed). Continue until Phase 2 exit conditions are fully met.

Also produce `spec.md` — the completed one-page spec with all fields filled in, formatted as a proper document.

Format each conversation turn in `session-log.md` as:

```
## Coach
[message]

## Sam
[reply]
```

At the end of `session-log.md`, add a section `## Phase 2 Complete` that states Phase 2 is signed off and lists what was agreed.
