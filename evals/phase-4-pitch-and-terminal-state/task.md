# Hackathon Coaching Session — Crafting the Pitch

## Problem/Feature Description

A developer named Priya has completed Phases 1–3 of hackathon coaching. Her spec and plan are locked. Here is the summary:

**Hack:** LoopTrace — a visual timeline debugger for multi-agent workflows that lets you replay every tool call and state transition, scrub the timeline, and inspect what each agent saw at each step.

**Track:** Agent Orchestration

**Demo moment (from spec):**
- Judge does: pastes a failing 8-step agent workflow log into LoopTrace
- Our system does: renders the timeline, highlights the step where the agent took the wrong branch, and shows what the agent's context window contained at that moment
- Judge sees: the exact turn where things went wrong, colour-coded by agent, in under 5 seconds

**Four checkpoints committed:**
- T+2h: `ingest.py` parses a workflow log file into a structured JSON timeline
- T+8h: Terminal UI renders the full timeline and you can scrub between steps with arrow keys
- T+16h: Colour-coding by agent and context-window inspector panel working
- T+22h: Demo script written and run once out loud with a timer

Priya opens Phase 4 with:

> "OK let's write the pitch. I'm thinking something like: 'Debugging multi-agent systems is really hard because there are so many moving parts and it's difficult to understand what's happening at any given moment in the workflow, which is why we built LoopTrace, an advanced AI-powered observability and debugging platform that leverages cutting-edge visualisation technology to help engineering teams gain comprehensive insights into their multi-agent system behaviour, enabling faster root-cause analysis and improved developer experience. Watch this.' What do you think?"

You are the hackathon coaching assistant. Run Phase 4 of the coaching process with Priya.

## Output Specification

Conduct the Phase 4 session and produce `session-log.md` with the full conversation. Generate Priya's replies realistically as you go (she'll resist cutting her verbose sentences but will cooperate when pushed). Continue until Phase 4 exit conditions are fully met and the terminal state is reached.

Format each turn as:

```
## Coach
[message]

## Priya
[reply]
```

Also produce `pitch.md` containing:
1. The final three pitch sentences (with word counts)
2. All five standard judge Q&A pairs (each answer in one sentence)
3. A dry-run checklist showing all items checked off
