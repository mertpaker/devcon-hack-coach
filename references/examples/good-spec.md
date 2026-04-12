# Worked Example: CacheScope (spec)

A fully worked example of the one-page spec, so you can see what "filled in properly" looks like. Track: **Context Engineering**.

Use this as a sanity check. If your spec is vaguer than this, tighten it. If it's broader than this, cut.

---

## Goal
Show backend engineers exactly which line of their prompt is busting the Anthropic cache, and what it's costing them every month.

## User
Backend engineers who maintain a production Anthropic integration, have already hit $1k+/month in API bills, and suspect something is wrong but can't point at it.

## Demo moment
- **Judge does:** pastes a real production prompt (two consecutive turns) into our CLI
- **Our system does:** diffs the two calls, highlights the one line that broke the cache, multiplies by observed request volume from the logs
- **Judge sees:** a red-highlighted line and the text **"This line cost you $340 last month"**

## What's in (max 3)
1. CLI that accepts two consecutive API requests and diffs their prompts at the block level
2. Cost estimator that multiplies the cache-bust by the user's observed request volume
3. One-click fix suggestion (usually: *"move this volatile field to the end of the system block"*)

## What's out
- ❌ A web dashboard *(tempting but eats the whole weekend)*
- ❌ Auto-patching the user's own code *(too risky in 24h, and judges will ask about it anyway)*
- ❌ Support for OpenAI / Gemini prompts *(scope creep — pick one provider and nail it)*

## Success in 24h
- [x] Working demo that runs end-to-end on stage
- [x] No blocker in the golden path
- [x] Pitch dry-run at least once with a timer

## Red flags
- ⚠️ Prompt caching behaviour differs between Claude Opus and Sonnet — pick **Sonnet 4.6**, document the assumption, move on
- ⚠️ Cost numbers must feel real, not hand-waved — pull from the Anthropic pricing page and cite it during the demo

---

*Spec locked. Moving to Phase 3.*
