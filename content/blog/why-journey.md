+++
title = "Why 'journey'"
date = 2026-08-25
weight = 2
description = "The naming story: why the primitive is called a journey — the round-trip requirement, the etymology, and a Swiss legal precedent running at national scale."
[taxonomies]
tags = ["naming"]
+++

Every artifact in the system belongs to one of two classes — the living product definition that governs, and the frozen record that explains — and they map cleanly onto an explorer leaving a village: the village is the permanent, shared home that every return improves, and the journey is the trip itself, with its departure, its adventure, and its return carrying goods and knowledge. The analogy fixes the *relationship* between the classes, not just their names: journeys exist to improve the definition, and records exist to explain how the definition got its shape.

## The round-trip requirement

The name was chosen before the two-class model existed, and it fit well enough. The two-class model turns the fit into a lock. The requirement is simple: **the primitive's name must promise a return that improves the departure point.** Very few candidate names do.

| Candidate | Why it fails |
|---|---|
| Task / ticket / issue | A unit of work to be disposed of. Completion is closure; nothing flows back. |
| Branch / PR | Names the code-half's plumbing, and is disposable by the methodology's own keystone (consensus never binds to code). |
| Epic | A big ticket: hierarchy without home; no return implied. |
| Quest | Strong on departure and adventure, but hero-centric — the world does not improve when the quest completes. |
| Expedition | Centers the outbound leg; an expedition may be one-way, with no implication that the home base is improved by what comes back. |
| Mission | Top-down assignment. Deliberation is not assigned: a mission has a commander, a journey has stakeholders. |
| Sprint | A time-box, not a unit of understanding — and the ceremony the methodology explicitly replaces. |
| **Journey** | Departure from home, adventure, return with gains. The home is part of the word's frame: a journey is defined by its round trip. An everyday word, zero jargon cost. |

## The etymological bonus

"Journey" is a double fit. It entered English around 1200 from Old French *jornee*, from Vulgar Latin *diurnum* — "a day's travel or work"; as late as Johnson's dictionary (1755), the primary sense was still "the travel of a day" (see [etymonline](https://www.etymonline.com/word/journey)). A day's travel is the archetypal round trip: you leave in the morning and are home by nightfall. The deep structure of the word is literally *out and back*.

The same root gives **journal** — the daily record of a journey. The methodology inherits the whole family for free: every journey produces a *journey record*, frozen at return, which becomes the product's lore — the decision timeline the next journey consults at departure. Trip and account-of-trip share a name because they share a root.

## A working precedent at national scale

The two-class split — frozen records versus a living consolidation — is not speculative. Switzerland has run a national-scale version for decades: the AS continuously since 1898, the SR as its maintained consolidation.

- The **Amtliche Sammlung (AS)** — the Official Compilation — publishes every federal act chronologically, as enacted. Entries never change. That is the record class: frozen, attributed, append-only provenance.
- The **Systematische Rechtssammlung (SR)** — the Classified Compilation — is the continuously maintained consolidation: organized by subject, amendments incorporated, repealed texts removed. That is the product definition: living, consolidated, the one everyone actually works from.

Every change in the SR traces back to frozen AS provenance — but the polarity is the instructive difference: in Swiss law it is inverted. There the frozen channel is constitutive (an act becomes binding only through promulgation in the AS; the SR is "lediglich Informationsmittel und hat keine negative Rechtskraft", PublG Art. 11). In this methodology the living definition is normative — **the definition wins, the record explains**: a product is legitimated by validated consensus and observable behavior, not promulgation, so the record's job is evidentiary. The precedent proves the split operable at the scale of a country's entire legal corpus, and marks the inversion of authority as a deliberate design decision, not an oversight.

## The vocabulary that follows

A name like this carries conventions:

- In normative text, say **Product Definition**, never village — the analogy is for onboarding and marketing; the methodology and its tooling say product definition.
- A **Record** is the frozen, journey-scoped artifact; a **Registry** is the living definition component it feeds.
- **Return** names the full act — fold the gains into the definition, freeze the journey into its record — while **merge** names the state transition in which the return culminates; the two are never used interchangeably.
- And the lifecycle gets a single frame: `departure → exploration → return`, layered over whatever the implementation calls its states.

The word was the cheapest part of the design. It does the most work per syllable: it promises a round trip, and it ships with its record.
