# Klyr

Klyr is a life-organizer / task-manager / project-manager designed from the ground up for people with ADHD: intuitive, easy to maintain, and built to help users actually do what they need and want to do — without pressure or shame.

## Repo state

Research phase complete. The design-research corpus in `research/` (29 docs, 553 cited sources) is the evidence base for every product decision. Product design and code have not started yet.

## Rules for agents working in this repo

1. **Before designing or building anything, route through [`research/INDEX.md`](research/INDEX.md).** Its task-routing table maps "I'm working on X" to the docs that should decide X — including the "also consider" docs you wouldn't think to check. Use it even for small decisions (copy tone, notification timing, empty states).
2. **[`research/product/design-principles.md`](research/product/design-principles.md) is binding.** 20 testable principles; treat violations as defects, not style debates. [`research/product/anti-patterns.md`](research/product/anti-patterns.md) is equally binding — it catalogs BANNED patterns (overdue shame stacks, streak hostage-taking, guilt copy, silent data loss, trial ambushes, punishment mechanics) with the alternatives to use instead.
3. **Ground decisions in the corpus.** Cite the relevant doc when justifying a choice. Never state a claim more confidently than the corpus does — evidence grades and status tags ([clinical] / [research] / [community] / [contested]) are part of the content, not decoration.
4. **Corpus edits follow [`research/_meta/CONVENTIONS.md`](research/_meta/CONVENTIONS.md)**: frontmatter contract, required sections, source tagging, myth screen, non-pathologizing tone, no fabricated numbers. When you add or rename a doc, update `INDEX.md` (tree, routing table, tag index); when you introduce a term, add it to `GLOSSARY.md` with a status tag.
5. **Not medical advice.** The corpus informs product design. Nothing in this repo diagnoses or treats, and Klyr's copy must never imply otherwise. See [`research/product/when-to-back-off.md`](research/product/when-to-back-off.md) for the wellness/medical boundary.

## Key entry points

| Need | File |
|---|---|
| Master navigation + task routing | `research/INDEX.md` |
| Corpus in 10 minutes | `research/00-executive-summary.md` |
| Binding design principles | `research/product/design-principles.md` |
| Banned patterns + alternatives | `research/product/anti-patterns.md` |
| Feature directions (evidence-graded) | `research/product/feature-directions.md` |
| Vocabulary with status tags | `research/GLOSSARY.md` |
| Provenance, limitations, trust calibration | `research/_meta/research-process.md` |
