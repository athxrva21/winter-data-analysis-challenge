# Is Australia Doing Well?
### A stress-tested well-being audit for the Winter Data Analysis Challenge 2026

> One country, three verdicts. We build a single well-being "score" for Australia — then spend the whole project trying to break it. The rank that survives every stress test is *"above average"*; the one that doesn't is *"among the best."* Beneath the flattering average sits the real finding: on the human dimensions of well-being, **Australia is not just declining, it is declining faster than almost the entire OECD.**

**The question, refined.** *"Is Australia doing well?"* is deliberately vague, so we sharpen it: **Australia looks comfortably above-average on a composite well-being score — is that verdict robust to how we measure, to which dimensions we count, and to which way the country is moving? And where it is slipping, is Australia sharing an OECD-wide trend or standing out as an outlier?**

---

## Key findings

1. **Australia is not one thing.** Standardised against the OECD, Australia is *best in the club* on voter turnout and top-ten on income and life expectancy — while simultaneously *bottom-quartile* on long working hours, negative emotions and heat exposure. Averaging these into one number erases the story.
2. **Only "above average" is robust.** The composite ranks Australia **14th of 38**. A 3,000-run Monte-Carlo stress test (measurement noise + indicator resampling) keeps it **above the OECD median in 89% of perturbed worlds, but in the top third only 44%** of the time. The single biggest lever is **compulsory voting** — remove that domain and Australia drops eight places.
3. **A two-speed nation.** Trends tested with **Mann-Kendall** and sized with **Theil–Sen** (both implemented from scratch): 7 of 13 are significant. Significantly *improving* — income, employment, life expectancy, falling work hours and gender wage gap. Significantly *worsening* — social support and deaths from suicide, alcohol and drugs.
4. **Australia is leading the decline, not sharing it.** Its rise in loneliness (+104%) and deaths of despair (+49%) outpaced roughly **89% of the OECD** — and on deaths of despair the OECD median actually *fell*. On its weakest dimensions, Australia is a negative outlier moving against the pack.
5. **The blind spot, filled.** Life-satisfaction data goes dark after 2020 — exactly where the trouble is. We fill that one gap with an external source (World Happiness Report): Australians' own life ratings have slid to a **record-low 6.97, 11th in the world.** A different survey, the same verdict.

**Wider context.** In 2023 the Australian Treasury launched *Measuring What Matters*, the nation's first national well-being framework, on precisely this premise — that GDP alone is inadequate. This analysis operationalises that idea and points at where the national conversation should go: not the income line, which is fine, but connection and distress.

---

## Repository contents

| File | Description |
|------|-------------|
| `Is_Australia_Doing_Well.ipynb` | **Main deliverable** — the reproducible report. Cleaning, methods, analysis and all six figures, executed end-to-end with narrative. |
| `Is_Australia_Doing_Well.html` | Rendered, read-only version of the notebook — open in any browser, no Python needed. |
| `VIDEO_SCRIPT.md` | Shot-by-shot script for the 3-minute submission video, timed and mapped to the judging criteria. |
| `OECD Data.csv` | Source data — OECD *How's Life?* Well-being Database extract (21 indicators, 47 countries, 2010–2025). |
| `oecd-well-being-database-definitions.pdf` | Official OECD indicator definitions and metadata (used to set indicator directionality). |
| `README.md` | This file. |

---

## Reproducing the analysis

The notebook is fully self-contained and depends on **only three libraries** — every statistic (Mann-Kendall, Theil–Sen, the Monte-Carlo perturbation) is implemented from scratch, so there is no `scipy`/`statsmodels` version drift.

```bash
# 1. Clone
git clone https://github.com/athxrva21/winter-data-analysis-challenge.git
cd winter-data-analysis-challenge

# 2. Install dependencies
pip install pandas numpy matplotlib jupyter

# 3. Run — keep OECD Data.csv beside the notebook
jupyter notebook Is_Australia_Doing_Well.ipynb   # then Run All
```

The notebook resolves the data path automatically as long as `OECD Data.csv` sits in the same folder. Run time is a few seconds; the Monte-Carlo is seeded, so results are deterministic.

---

## Method in brief

- **Cleaning.** The raw SDMX export ships every field twice; the human-readable value column is empty, so we use the machine columns (`OBS_VALUE`, `TIME_PERIOD`), coerce types, and retain the `OBS_STATUS` quality flags rather than dropping estimated/provisional points.
- **Directionality.** Every indicator is oriented (+1 higher-is-better, −1 lower-is-better) from the OECD metadata, so a suicide rate and a satisfaction score can share a scale.
- **Standardisation.** Each indicator is z-scored across OECD members using each country's latest 2021–24 value; the composite is the mean of domain-level z-scores (equal weight per domain).
- **Robustness.** Ranking is stress-tested with a seeded 3,000-run Monte-Carlo (Gaussian noise + indicator bootstrap) and leave-one-domain-out. Trends use Mann-Kendall significance and Theil–Sen slopes.
- **External data** is used narrowly — one series, to fill one identified gap (post-2020 subjective well-being).

---

## Data sources

- **OECD, *How's Life?* Well-being Database** — national well-being indicators, 2010–2025. <https://data-explorer.oecd.org>
- **World Happiness Report / Gallup World Poll** — Cantril-ladder life evaluations (used to fill the post-2020 life-satisfaction gap). <https://worldhappiness.report>
- **Australian Treasury, *Measuring What Matters* (2023)** — national well-being framework, cited as wider context. <https://treasury.gov.au/policy-topics/measuring-what-matters>

---

*Built for the Winter Data Analysis Challenge 2026. Analysis and figures are reproducible from the notebook and the included data.*
