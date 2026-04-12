# Worked Example: CacheScope (pitch)

The 3-sentence pitch and judge Q&A for the CacheScope spec in `good-spec.md`. Use it as a shape reference.

---

## Sentence 1 — The wedge
*"When you add a timestamp to your Claude system prompt, you silently burn your entire prompt cache on every call."*

**17 words.** Names a real mistake engineers make this week.

## Sentence 2 — The move
*"We built CacheScope — a CLI that diffs two API calls and tells you exactly which line cost you money."*

**19 words.** One noun (CacheScope), one verb (diffs), concrete outcome (which line cost you money). No adjectives.

## Sentence 3 — The moment
*"Watch this."*

Then run the live demo. Paste a real prompt. Red line. "$340 last month." Done.

**Total demo time: 50 seconds.** Do not speak during the demo — let the red line do the work.

---

## Judge Q&A prep

### The standard five

1. **How does this scale?**
   > We read request logs once and run the diff offline. Every engineer on the team gets a personal report; the analysis is cheap.

2. **Why not just use Helicone or LangSmith?**
   > Those tools show you *total spend*. We show you the exact *line of code* that caused the spike, so you can fix it without archaeology.

3. **What happens when the LLM hallucinates?**
   > Irrelevant — we're doing static analysis of your prompts, not running inference. There's no LLM in the hot path.

4. **Who pays for this?**
   > The same budget that pays the API bill. We sell it as a cost-cutter, not a dev tool, so it comes out of ops spend, not engineering spend.

5. **What's your moat?**
   > We plug into CI. Every PR shows a diff of *"this change would cost you $X/month in extra cache busts"*. Once that diff is in the PR template, you're the default.

### Hack-specific three

- **Does it support streaming responses?**
  > Yes — we diff the request side, not the response, so streaming doesn't matter.

- **What about function calling / tool use?**
  > Tools are cached together with the system block — we treat tool schemas as part of the cache surface and diff them the same way.

- **Why only Anthropic?**
  > Because Anthropic's prompt caching is the most aggressive and therefore the most punishing to bust. We ship with the one provider where the ROI is most visible; other providers are week 2.

---

## Dry-run checklist

- [x] Each of the 3 sentences is under 20 words
- [x] Sentence 3's live demo matches the spec's Demo moment exactly
- [x] All 5 standard Q&A answered in one line
- [x] Pitch run out loud, once, with a timer — came in at **1m 42s**, under the 2-minute cap
