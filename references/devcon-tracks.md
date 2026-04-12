# AI Native DevCon — Track Cheat Sheet

Four tracks. Pick one. Your hack lives inside it.

Use this file when the user is unsure which track fits their itch, or when you need to propose three concrete hack angles in Phase 2.

---

## 1. Context Engineering

The discipline of giving an agent *exactly the right information at exactly the right moment*. RAG done well. Prompt caching strategy. Retrieval budgets. Tool documentation that lives in the context window. How to fit a 500-file codebase into 200k tokens without lying to yourself.

**Keywords:** RAG, retrieval, prompt caching, context window, grounding, embeddings, chunking, token budget, tool docs in context

**Example hack angles:**

- **CacheScope** — a CLI that diffs two consecutive API calls and highlights the single line that busted the prompt cache, in red, with the estimated monthly cost impact.
- **RetrieveReplay** — records every retrieval your agent does during a session, then lets you replay the run with a different retrieval strategy and compare outputs side by side.
- **ContextMirror** — shows the agent exactly what *it* can see right now — a live view of the current context window, with colour-coded sources (system, retrieved docs, tool output, user turn).

**Anti-patterns (don't pitch these as Context Engineering):**
- Building a new embedding model — too big for 24h, and not really context engineering
- A generic chatbot — chat isn't a context strategy
- "We prompt-engineered it" — prompt engineering is a means, not a deliverable

---

## 2. Agent Orchestration

Coordinating multiple agents or long-running workflows. Parallel fan-out. Checkpointing and recovery. Dead-letter queues for agent failures. Routing between specialist agents. What happens when step 7 of 12 fails at 3am.

**Keywords:** multi-agent, workflow, parallel, checkpoint, resume, routing, handoff, dead-letter, long-running, retries, idempotency

**Example hack angles:**

- **LoopScope** — a visual debugger for agent loops that replays every turn, every tool call, and every state transition as a timeline you can scrub.
- **FanOut** — a scheduler that takes one research question, fans it out to N parallel sub-agents with bounded concurrency, and merges the answers with conflict detection.
- **CheckpointKit** — a tiny library that makes any LangGraph-style agent resumable from the last successful node, with one decorator.

**Anti-patterns:**
- Single-turn chat (that's not orchestration)
- Pure prompt engineering dressed up as "workflow"
- A generic job queue that happens to run agents — show the *agent-shaped* difficulty

---

## 3. Agent Enablement Platform

The *infrastructure* for building and running agents. Sandboxes. Observability. Evals. Deployment. Permission systems. Test harnesses. The stuff a platform team would build so product teams stop rebuilding it.

**Keywords:** sandbox, observability, evals, permissions, audit log, test harness, SDK, platform, deploy, isolation

**Example hack angles:**

- **SandboxCLI** — a one-command sandbox where agents can run shell commands safely, with a full audit log and a hard-fail tripwire on any `rm -rf`, `curl | sh`, or egress outside the allow-list.
- **EvalsInCI** — a GitHub Action that runs your agent against a frozen test suite on every PR and posts a diff of pass/fail changes as a review comment.
- **AskBeforeAct** — a permission-request surface: before an agent does anything destructive, it shows the user a one-line "I want to do X, OK?" with a keyboard shortcut for approve/deny.

**Anti-patterns:**
- A single-purpose end-user agent — that's a product, not a platform
- "We deployed a model" — deployment alone isn't enablement
- Vendor wrappers with no distinct contribution

---

## 4. Organizational Enablement

Teams adopting AI-native workflows. Change management. Developer experience with agents. Metrics that show the business the agents earned their keep. Governance, training, review culture. How humans and agents collaborate inside a real engineering org.

**Keywords:** DX, adoption, metrics, governance, review, training, team, collaboration, workflow, ROI, culture

**Example hack angles:**

- **AgentLedger** — a Slack bot that tracks which engineers used which AI tools on which PRs, and produces a weekly "hours saved" leaderboard based on measured PR-cycle time deltas.
- **ReasoningPR** — a PR template that enforces an "agent reasoning" section, with a linter that fails the PR if the agent's reasoning wasn't captured.
- **OnboardingCopilot** — a skill-building coach for junior devs pair-programming with AI, that nudges them to explain *why* the agent's suggestion is correct before accepting it.

**Anti-patterns:**
- A pure technical tool with no team dimension
- Compliance-only plays with no developer upside
- Dashboards that don't drive a decision

---

## How to match an itch to a track

If the user's itch is about:

- **Data going in and out of prompts** → Context Engineering
- **Multiple steps, multiple agents, or things running for more than one turn** → Agent Orchestration
- **The infrastructure to make *other people's* agents possible** → Agent Enablement Platform
- **Humans and teams using AI (not just one dev alone)** → Organizational Enablement

If it sits on a boundary, pick the one whose *judges* will care most. Don't try to claim two tracks — that dilutes the pitch.
