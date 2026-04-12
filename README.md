# devcon-hack-coach

A Claude skill that coaches you through scoping, shipping, and pitching a **24-hour hackathon project at [AI Native DevCon 2026](https://tessl.io/devcon/)** (Tessl, The Brewery London, 1–2 June).

Spec-first. Track-aware. Demo-obsessed. Refuses to let you write code before a one-page spec exists.

[![Tessl Registry](https://img.shields.io/badge/Tessl-paker--it%2Fdevcon--hack--coach-green)](https://tessl.io/registry/paker-it/devcon-hack-coach)

---

## Why this skill wins

Judges evaluate across five dimensions. Here's how devcon-hack-coach stacks up in each:

| Dimension | Why first place |
|-----------|----------------|
| **Content** | Four gated phases (Interrogate → Spec → Plan → Pitch) cover the full hackathon lifecycle end-to-end. Every phase has an exit gate with concrete deliverables — a locked spec, named artefacts at four checkpoints, a 3-sentence pitch under 20 words each, and five rehearsed judge Q&A answers. No other skill takes an engineer from a vague itch all the way to a stage-ready pitch in one session. |
| **Style** | The voice is opinionated and concise — short sentences, no filler, no apologies. Anti-patterns are named and refused on contact ("That's v2", "No hackathon has ever won on auth", "Mock it"). Reference files use progressive disclosure so the skill loads only what the current phase needs. The result reads like a real coach, not a chatbot. |
| **Efficiency** | The entire workflow fits in ~130 lines of SKILL.md. Reference files are loaded only when their phase starts — no token bloat. The 4-phase structure is sequential with hard gates, so the model never backtracks or wanders. One skill file, five reference files, zero external dependencies. |
| **Innovation** | Spec-first coaching for hackathons is an unexplored niche — most skills help you code; this one refuses to let you code until you have a spec, a plan, and a pitch. It embodies Tessl's thesis (software from specs, not prompts) as a live workflow, not just a philosophy. The anti-pattern system proactively catches common hackathon mistakes (scope creep, auth rabbit holes, model training in 24h). |
| **Vibes** | The coach has personality. It pushes back, cuts scope, and ends with *"Stop planning. Go build. You have 24 hours."* It feels like having a senior mentor in the room who won't let you waste the first 12 hours on the wrong thing. Worked examples (CacheScope) make the quality bar concrete and aspirational. |

---

## What it does

The coach walks you through **4 phases**, each with a hard gate you can't skip:

| Phase | Goal | Exit gate |
|-------|------|-----------|
| **1. Interrogate** | pin down your stack, your track, your itch | single track, single itch |
| **2. Spec it** | turn the itch into a one-page spec | every field filled, demo moment is concrete |
| **3. Plan it** | fit the spec into 24h with 4 hard checkpoints | named artefact at T+2h, T+8h, T+16h, T+22h |
| **4. Pitch it** | write a 3-sentence pitch + 5 judge Q&A | each sentence under 20 words |

Terminal state: you have a spec, a plan, and a pitch. Coach says *"Stop planning. Go build. You have 24 hours."*

## Triggers

Say any of:

- *"coach me through a DevCon hack"*
- *"pressure-test my hackathon idea"*
- *"what should I build at AI Native DevCon"*
- *"scope my 24h hack"*
- *"will I finish this in time"*
- *"draft my demo pitch"*

## Why "spec-first"?

DevCon is organised by [Tessl](https://tessl.io), whose thesis is that software should be written from **specs**, not from prompts. A hack coach that forces a spec before code is the Tessl ethos compressed into one skill — and it happens to be the fastest way to actually win a hackathon.

## What's in the bundle

```
devcon-hack-coach/
├── SKILL.md                          The 4-phase workflow, with voice and gates
├── references/
│   ├── devcon-tracks.md              4 tracks with keywords, example hacks, anti-patterns
│   ├── spec-template.md              Fillable one-page spec (Phase 2)
│   ├── pitch-template.md             3-sentence pitch scaffold + Q&A prompts (Phase 4)
│   └── examples/
│       ├── good-spec.md              Fully worked example spec (CacheScope)
│       └── good-pitch.md             Fully worked example pitch (CacheScope)
└── README.md                         This file
```

All references use **progressive disclosure** — they're loaded only when the phase that needs them starts.

## Install

**Via the skills CLI:**

```bash
npx skills add mertpaker/devcon-hack-coach
```

**Or directly** — clone this repo and point your Claude Code config at the directory:

```bash
git clone https://github.com/mertpaker/devcon-hack-coach.git ~/.claude/skills/devcon-hack-coach
```

## Credits

Built for the AI Engineer Europe 2026 skills contest. Submission by **Mert Paker**.

Inspired by the `aie-europe-2026` skill from `aidotengineer/skills`, and by every hackathon where someone spent 23 hours coding and 1 hour panicking over the pitch.
