# devcon-hack-coach

A Claude skill that coaches you through scoping, shipping, and pitching a **24-hour hackathon project at [AI Native DevCon 2026](https://tessl.io/devcon/)** (Tessl, The Brewery London, 1–2 June).

Spec-first. Track-aware. Demo-obsessed. Refuses to let you write code before a one-page spec exists.

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
