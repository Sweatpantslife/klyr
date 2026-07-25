# Klyr

**An ADHD-first life organizer, task manager, and project manager.**

Klyr is being designed from the ground up for people with ADHD — not a generic to-do app with an "ADHD mode" bolted on. The goal: a system that feels intuitive, stays easy to maintain, and helps you actually do what you need and want to do — without pressure, without shame, and without collapsing the first week you ignore it.

## Status: research phase complete

Product design has not started yet. What exists today is the **design-research corpus** that will drive every product decision: **29 documents, 553 cited sources**, produced by a multi-agent research pipeline (peer-reviewed studies, clinical experts, and labeled lived-experience sources) and audited in three independent passes for scientific accuracy, coherence, and navigability.

**Start at [`research/INDEX.md`](research/INDEX.md)** — or read the [10-minute executive summary](research/00-executive-summary.md).

| If you want... | Go to |
|---|---|
| The whole argument in 10 minutes | [research/00-executive-summary.md](research/00-executive-summary.md) |
| The binding design principles (20) | [research/product/design-principles.md](research/product/design-principles.md) |
| What Klyr must never do (24 anti-patterns) | [research/product/anti-patterns.md](research/product/anti-patterns.md) |
| 45 evidence-grounded feature directions | [research/product/feature-directions.md](research/product/feature-directions.md) |
| Why existing apps fail ADHD users | [research/product/app-landscape.md](research/product/app-landscape.md) |
| The science: EF, dopamine, time, memory, attention, emotion | [research/foundations/](research/foundations/) |
| Term lookup with evidence-status tags | [research/GLOSSARY.md](research/GLOSSARY.md) |

## The one-paragraph thesis

ADHD is a performance problem, not a knowledge problem — people know exactly what to do and cannot reliably make themselves do it at the right time. Mainstream productivity tools assume the opposite: they externalize nothing, punish inconsistency, demand maintenance rituals, and turn every lapse into a wall of red overdue badges. That is why the median tool is abandoned within days, and why the ADHD community cycles through system after system. Klyr's bet, grounded in this corpus: act as an external executive system (hold time, memory, and motivation in the environment, at the point of performance), make starting trivial, make coming back after a lapse the celebrated core loop — and never, ever ship shame.

## Repo map

- `research/` — the design-research corpus (start at [`INDEX.md`](research/INDEX.md))
- `research/_meta/` — corpus conventions and provenance
- `CLAUDE.md` — working guide for AI agents contributing to this repo

## Planned next phases

1. Product vision and scope, grounded in [`feature-directions.md`](research/product/feature-directions.md)
2. Design system and prototypes, bound by [`design-principles.md`](research/product/design-principles.md) and [`anti-patterns.md`](research/product/anti-patterns.md)
3. Build
