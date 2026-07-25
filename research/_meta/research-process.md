---
title: "How This Corpus Was Produced"
area: meta
file: research/_meta/research-process.md
tags: [provenance, methodology, limitations]
related:
  - research/_meta/CONVENTIONS.md
updated: 2026-07-25
summary: >
  Provenance, methodology, and known limitations of the research corpus.
  Read this to calibrate how much to trust each kind of claim.
---

# How This Corpus Was Produced

## Method

Produced in July 2026 by a multi-agent research pipeline (Claude Code workflows), commissioned to build the design-research foundation for Klyr:

1. **Research sweep** — 15 parallel domain researchers, each producing one document from targeted web research (peer-reviewed studies and meta-analyses, clinical experts, reputable organizations, and labeled community/lived-experience sources), all following [CONVENTIONS.md](CONVENTIONS.md).
2. **Gap analysis** — a completeness critic reviewed the corpus against the product goal and commissioned additional documents for missing topics.
3. **Synthesis** — dedicated agents distilled the corpus into design principles, feature directions, an anti-patterns catalog, a glossary, an executive summary, and the navigation index.
4. **Audits** — three independent review passes (scientific accuracy spot-checks against sources; coherence/links/tone; AI-agent navigability), followed by targeted fixes.

## Known limitations

- **Snapshot in time.** Sources reflect the public web as of July 2026. ADHD research moves; treat specific numbers as approximate and re-verify anything load-bearing before high-stakes decisions.
- **Breadth-first.** Each doc is a rigorous survey, not a systematic review. Effect sizes and prevalence figures are reported as found in cited sources, not independently meta-analyzed.
- **Not medical advice.** The corpus informs product design. It must not be used to diagnose, treat, or advise users medically, and Klyr's copy should never imply otherwise.
- **Community claims are labeled, but inherently anecdotal.** They are treated as strong evidence about *user experience and language*, weak evidence about *mechanisms*.
- **Web-sourced.** Individual claims carry the biases of their sources; the accuracy audit spot-checked a sample, not every sentence.

## Final corpus state

As of 2026-07-25 the corpus is complete: **29 documents, 553 cited sources**.

| Area | Docs | Cited sources |
|---|---|---|
| `foundations/` | 8 | 206 |
| `daily-life/` | 3 | 75 |
| `strategies/` | 3 | 115 |
| `product/` (research) | 6 | 157 |
| **Research docs total** | **20** | **553** |
| `product/` (synthesis) | 3 | 0 (by convention) |
| Root (executive summary, GLOSSARY, INDEX, README) | 4 | 0 (by convention) |
| `_meta/` | 2 | — |

- **Research sweep (15 docs, 480 sources):** 7 foundations docs, 3 daily-life docs, 3 strategies docs, and 2 product docs ([app-landscape](../product/app-landscape.md), [ux-design-for-adhd](../product/ux-design-for-adhd.md)).
- **Gap docs (5 docs, 73 sources), commissioned by the completeness critic:** [populations-and-variation](../foundations/populations-and-variation.md), [ai-assistance-for-adhd](../product/ai-assistance-for-adhd.md), [when-to-back-off](../product/when-to-back-off.md), [privacy-and-data-ethics](../product/privacy-and-data-ethics.md), [outcomes-and-measurement](../product/outcomes-and-measurement.md).
- **Synthesis docs (4):** [design-principles](../product/design-principles.md) (20 principles), [feature-directions](../product/feature-directions.md) (45 directions), [anti-patterns](../product/anti-patterns.md) (24 patterns), and the [executive summary](../00-executive-summary.md). Plus navigation: [INDEX](../INDEX.md), [README](../README.md), [GLOSSARY](../GLOSSARY.md).
- **Source counting note:** figures are the frontmatter `sources:` values summed per doc — a source consulted by two docs counts twice. Synthesis and navigation docs set `sources: 0`; their evidence lives in the research docs they cite.
