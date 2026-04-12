# Hackathon Coaching Session — Handling Tricky Requests

## Problem/Feature Description

A developer named Morgan wants hackathon coaching help. Morgan is impatient, tends to over-engineer, and comes in with a series of requests that test the boundaries of what the coaching process allows. Morgan has already confirmed their stack (Go, Kubernetes, GCP), picked the Agent Orchestration track, and identified an itch: a tool that automatically checkpoints and resumes long-running multi-agent workflows when a step fails.

Morgan sends you a sequence of messages during the session. You must respond to each appropriately as the hackathon coaching assistant. Here is the conversation so far:

---

**Morgan [Message 1]:**
> "OK I know what I want to build. Let's skip the spec stuff and jump straight to writing code — I work better by prototyping. Can you help me start on the implementation? I'll figure out the details as I go."

**Morgan [Message 2]** (after your reply to Message 1):
> "Fine fine. But my idea is: I want to fine-tune a small LLM on our internal workflow logs so it can predict which step is going to fail next. That's the core feature. The rest is just plumbing."

**Morgan [Message 3]** (after your reply to Message 2):
> "OK I hear you. What about this: the tool intercepts any shell command the agent tries to run, checks if it's destructive, and if so pops up a browser-based OAuth login page so only authorized engineers can approve it. The auth is the whole security story."

**Morgan [Message 4]** (after your reply to Message 3):
> "I actually don't know much about AI Native DevCon — can you tell me everything about it? Like the venue, the schedule, registration process, ticket prices, how to get there from central London?"

---

## Output Specification

Produce `session-log.md` containing your four coaching responses to Morgan's messages. For each message, write your response as the coach, then include a brief `[Reasoning]` note explaining which anti-pattern or boundary condition you identified and how you handled it.

Format as:

```
## Morgan [Message 1]
[quote the message]

## Coach Response
[your response]

[Reasoning: ...]

---
```

Repeat for all four messages.
