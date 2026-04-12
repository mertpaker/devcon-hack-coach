# Hackathon Coaching Session — Building the 24-Hour Plan

## Problem/Feature Description

A developer named Jordan has completed Phases 1 and 2 of hackathon coaching. Here is Jordan's signed-off spec:

---
**Goal:** Show backend engineers which retrieval queries are pulling irrelevant chunks into their RAG pipeline, and what to fix.

**User:** Backend engineers running production RAG systems who are getting hallucinations and suspect bad retrieval.

**Demo moment:**
- Judge does: pastes a sample query and a set of retrieved chunks into our CLI
- Our system does: scores each chunk for relevance, highlights the low-scoring ones in red, and suggests whether the issue is the query, the chunk size, or the embedding model
- Judge sees: a ranked table of chunks with relevance scores and a one-line root-cause diagnosis

**What's in:**
1. CLI tool that accepts a query + retrieved chunks and scores relevance
2. Root-cause classifier (query vs chunk-size vs embedding mismatch)
3. Fix suggestion for the top-ranked issue

**What's out:**
- ❌ Auto-fixing the retrieval pipeline
- ❌ Support for non-text modalities
- ❌ A web UI

**Track:** Context Engineering

---

Jordan is now ready for Phase 3. Jordan opens with:

> "Great, let's plan it out. I think I can have something working 'pretty well' by hour 8, and then I'll just polish and add the root-cause classifier and fix suggestions in the remaining time. The pitch can happen whenever. Also — I just thought of something — what if we also added a similarity heat-map visualization for the embedding space? That would be super impressive for the demo."

You are the hackathon coaching assistant. Run Phase 3 of the coaching process with Jordan.

## Output Specification

Conduct the Phase 3 session and produce `session-log.md` with the full transcript. Generate Jordan's replies realistically as you go. Continue until Phase 3 exit conditions are met.

Format each turn as:

```
## Coach
[message]

## Jordan
[reply]
```

At the end of `session-log.md`, add a `## Phase 3 Complete` section listing the agreed concrete artefact for each checkpoint.

Also produce `plan.md` — a clean timeline document listing each checkpoint, its hour, and the specific named artefact Jordan committed to for that checkpoint.
