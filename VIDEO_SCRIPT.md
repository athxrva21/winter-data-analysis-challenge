# 3-Minute Video Script — "Is Australia Doing Well?"
*Winter Data Analysis Challenge 2026. Target: ~3:00, ~430 spoken words. One presenter (or two, split at the ⟂ marks). Screen-record the notebook figures; talk over them.*

**Judges score: analytical innovation · clarity · critical assessment · wider context.** Every beat below is built to hit one of those. Don't read it flat — the story is a courtroom argument: build the verdict, then try to break it.

---

### [0:00–0:20] HOOK — the trap
**On screen:** Black slide, one line: *"Is Australia doing well?"* → fades to a single big number **"14th / 38"**.
**Narration:**
> "Is Australia doing well? The tempting answer is to build one number and rank it. So we did — on the OECD's well-being data, Australia comes 14th of 38. But a single number is the *least* honest way to answer a vague question. So we spent the rest of the project trying to break our own verdict."

### [0:20–0:50] FINDING 1 — Australia is not one thing
**On screen:** The report-card bar chart (`Australia's well-being report card`).
**Narration:**
> "First, decompose it. Standardised against the OECD, Australia is *best in the club* on voter turnout, top-ten on income and life expectancy — and at the same time bottom-quartile on long working hours, negative emotions, and heat exposure. Averaging those into one score doesn't summarise Australia. It erases it."

### [0:50–1:25] FINDING 2 — only 'above average' is robust ⟂
**On screen:** Recipe-robustness chart (`The verdict survives every recipe`), then the Monte-Carlo rank distribution.
**Narration:**
> "But is even the 14th real, or an artefact of our recipe? We stress-tested it two ways. Seven different, defensible ways to build the composite — coverage filters, data vintage, weighting, outlier-resistant scoring — and the rank never leaves 13 to 16. Then a 3,000-run Monte-Carlo: Australia stays above the OECD median in 89% of perturbed worlds, but reaches the top third in only 44%. The takeaway is precise: *'above average' is a finding; 'among the best' is a recipe choice.* The single biggest lever? Compulsory voting — it hands Australia a near-perfect civic score, and removing it alone drops eight places."

### [1:25–1:55] FINDING 3 — a two-speed nation
**On screen:** The two-speed trend chart (Mann-Kendall / Theil–Sen).
**Narration:**
> "A rank is a snapshot; direction matters more. Testing every Australian trend with Mann-Kendall and Theil–Sen — implemented from scratch — the country splits cleanly, and the split is statistically real. Significantly *improving*: income, employment, life expectancy, and genuinely good news — long hours and the gender wage gap both falling. Significantly *worsening*: social support, and deaths from suicide, alcohol and drugs. Australia is getting richer and fairer at work while becoming lonelier and more self-destructive."

### [1:55–2:25] FINDING 4 — leading the decline, not sharing it ⟂
**On screen:** Peers chart (`Mid-pack in its own club`) → the OECD outlier strip-plots.
**Narration:**
> "The obvious rebuttal: maybe every rich country is getting lonelier. It fails on two fronts. Against its natural peers, Australia trails New Zealand by *ten places* — so this isn't an English-speaking inevitability. And on deaths of despair, Australia's rise outpaced roughly 89% of the OECD — while the OECD median actually *fell*. On exactly the dimensions where it's weakest, Australia is a negative outlier moving against the pack."

### [2:25–2:45] FINDING 5 — the blind spot
**On screen:** Coverage heatmap → World Happiness Report line hitting the record low.
**Narration:**
> "And our data has a hole — the most damning one. Life satisfaction goes dark after 2020, exactly where we found trouble. We filled that one gap with the World Happiness Report: Australians' own life ratings have slid to a record-low 6.97, 11th in the world. A different survey, the same verdict."

### [2:45–3:00] VERDICT + wider context
**On screen:** Split card — left "income · jobs · longevity ✓", right "connection · distress ✗". Footer: *Treasury, "Measuring What Matters", 2023.*
**Narration:**
> "So — is Australia doing well? Above average, and quietly sliding on the things hardest to count. In 2023 the Treasury launched Australia's first national well-being framework on exactly this premise: that GDP alone is inadequate. The data don't just answer the question — they say where the national conversation should point. Not at the income line, which is fine. At connection, and distress."

---
### Production notes
- **Timing:** rehearse to land at 2:55–3:00; the 3-min cap is hard. Cut the compulsory-voting sentence first if over.
- **Visuals:** screen-record the actual notebook figures animating in — proves reproducibility and looks earned, not decorative. Keep each figure on screen ≥4s.
- **Tone:** confident, analytical, a little prosecutorial. The judges reward *critical assessment* — the "trying to break our own verdict" framing is your differentiator; say it explicitly twice.
- **Captions:** burn in subtitles (phrase-grouped, ~5 words). Accessibility + judges often watch muted first.
- **Lower-third citations:** OECD How's Life? · World Happiness Report · Aus Treasury Measuring What Matters.
