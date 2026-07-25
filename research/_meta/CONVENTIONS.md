---
title: "Research Corpus Conventions"
area: meta
file: research/_meta/CONVENTIONS.md
tags: [conventions, contributing, format]
related:
  - research/_meta/research-process.md
sources: 0
updated: 2026-07-25
summary: >
  The format, sourcing, and tone contract for every document in research/.
  Read this before adding or editing any corpus doc.
---

# Research Corpus Conventions

How documents in `research/` are structured, sourced, and maintained. Follow these rules when adding or editing any doc. For AI agents: this file is the contract that makes the corpus predictable to navigate — every doc obeys it, so you can rely on it.

## Purpose of the corpus

This corpus is the evidence base for every design decision in **Klyr** — a life organizer / task manager / project manager designed from the ground up for people with ADHD. The goal of the product: feel intuitive, stay easy to maintain, and help users actually do what they need and want to do — without pressure or shame.

Docs are written for the *builders* of Klyr (AI agents and humans): rigorous, specific, actionable. The corpus is not medical advice and is not end-user content.

## Directory layout

| Path | What lives there |
|---|---|
| `research/INDEX.md` | Master navigation, including a task→docs routing table. **Always start here.** |
| `research/00-executive-summary.md` | The whole corpus in ~10 minutes. |
| `research/GLOSSARY.md` | Term lookup with status tags and links to deep-dive docs. |
| `research/README.md` | What this corpus is and how to use it. |
| `research/foundations/` | The science: mechanisms of ADHD (executive function, dopamine, time, memory, attention, emotion). |
| `research/daily-life/` | How ADHD plays out day to day — the problems Klyr exists to solve. |
| `research/strategies/` | What helps: interventions, planning systems, motivation techniques — with evidence grades. |
| `research/product/` | Market landscape, UX guidance, and the Klyr synthesis docs (design principles, feature directions, anti-patterns). |
| `research/_meta/` | This file, plus how the corpus was produced. |

## Document format

Every doc starts with YAML frontmatter:

```yaml
---
title: "Time Perception and Time Blindness in ADHD"
area: foundations            # foundations | daily-life | strategies | product | root | meta
file: research/foundations/time-perception.md   # repo-relative path to self
tags: [time-blindness, temporal-discounting, scheduling, deadlines]
related:
  - research/foundations/executive-function.md
  - research/strategies/evidence-based-strategies.md
sources: 14                  # number of cited sources
updated: 2026-07-24
summary: >
  One or two sentences describing what the doc covers and when to read it.
---
```

Required sections, in order:

1. `# <Title>`
2. `## TL;DR` — 6–12 bullets. The whole doc in miniature; a reader in a hurry reads only this.
3. Body sections (H2/H3 of the author's choice; short paragraphs; tables where they genuinely compress; bold key terms on first use).
4. `## Design implications for Klyr` — numbered, concrete, testable implications. **The most important section of every doc.**
5. `## Open questions` — optional but encouraged: what research doesn't settle, what needs user testing.
6. `## Sources` — numbered markdown links, each tagged with a source type (below). Only sources actually consulted.

Synthesis docs (`design-principles`, `feature-directions`, `anti-patterns`, `GLOSSARY`, the executive summary, `INDEX`) may replace the body/implications sections with their own structure, but keep frontmatter; `INDEX.md`, `GLOSSARY.md`, and the `_meta/` docs are exempt from `## TL;DR` (the `_meta/` docs carry `sources: 0` like other non-research docs).

## Evidence and sourcing rules

- **Source hierarchy:** meta-analyses & peer-reviewed research > clinical experts & major orgs (CHADD, ADDitude, NICE, APA) > quality journalism > community/lived experience.
- **Tag every source:** `[research]` peer-reviewed/academic · `[clinical]` clinician-authored or org guidance · `[community]` lived experience, forums, creators, coaches · `[product]` app sites, reviews, market data.
- **Community concepts belong here** (e.g. *waiting mode*, *RSD*, *"object permanence" issues*, *ADHD tax*) — they encode real UX truth — but must carry an explicit status label (community term / clinical heuristic / contested / not in DSM).
- **Never fabricate.** No invented statistics or citations; a number you can't source is a number you delete. When evidence is thin, mixed, or contested, say so inline ("evidence: mixed").
- **Myth screen:** known pop-science myths must not appear as fact (dopamine "deficit"/"detox" absolutes, 21-day habit rule, learning styles, left/right-brained people).
- **Links:** cite the URLs actually consulted; use repo-relative links for cross-references between docs.

## Tone

- Non-pathologizing and strengths-aware. People *have ADHD* or *are ADHDers* (both fine); never "sufferers"; no moralizing ("just needs discipline").
- Written for a smart generalist building a product; define clinical terms on first use (and add them to `GLOSSARY.md`).
- Specific beats general. Mechanisms, numbers, named effects and researchers — not vibes.
- American spelling, consistently.

## Adding or changing a doc

1. Follow the format above; place the doc in the right area directory.
2. Add cross-links: your doc links its `related:` docs inline where relevant, and `INDEX.md` must list it (update the annotated tree, the routing table if relevant, and the tag index).
3. Keep `updated:` and `summary:` accurate — navigation is built from frontmatter.
4. If you introduce a term, add it to `GLOSSARY.md` with a status tag.
5. Never state a claim more confidently than its source does.
