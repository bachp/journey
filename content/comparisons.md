+++
title = "Comparisons"
description = "A condensed map of the landscape as partial implementations: trunk-based development, OpenSpec, Spec Kit, Kiro — and the one-line verdicts."
weight = 4
+++

The methodology is a protocol, not a file format — and the landscape already contains working pieces of it. Each entry below is a **partial implementation** of the same data-model half: a specific structuring of the product definition and of the deltas, exactly the two things the methodology leaves implementation-defined. None implements the protocol half — consensus semantics and a provenance regime. The three [invariants](/invariants/) are the test that decides how much of the methodology each one realizes.

**Trunk-based development** (+ feature flags) is the topology the methodology generalizes: one trunk, short-lived branches, integrate back, collision means rebase and re-run. The one lift: the trunk carries the whole product description, not just code — and the journey, taking the place of the branch, covers the whole product too. Flags underneath remain the right tool for exposure control; they tell you the artifact isn't hurting users, never that stakeholders agreed it should exist.

**The spec-driven tools** — OpenSpec, Spec Kit, Kiro — are the solo corners of the space: one human, one AI, and the data-model half done well.

| Approach | What it implements | What it assumes away |
|---|---|---|
| [OpenSpec](https://github.com/Fission-AI/OpenSpec) | Living specs plus ADDED/MODIFIED/REMOVED deltas that merge on archive — a proven behavior-registry core, at solo scale | Consensus: one voice, no gates, no provenance of consent; the conversation is deliberately disposable |
| [Spec Kit](https://github.com/github/spec-kit) | A constitution-to-tasks pipeline with real intent artifacts | Consensus maturity: the gates gate document production, not agreement — the phases stay phases |
| [Kiro](https://kiro.dev) | Executable specs and agent hooks inside a commercial IDE | The organization: automates the developer's workflow, and its spec-sync direction (code → doc) quietly institutionalizes the drift the methodology exists to prevent |

The one-line verdicts:

- **OpenSpec** is the journey with the consensus problem assumed away.
- **Spec Kit** is waterfall re-tooled for agent throughput — it keeps the phase the methodology abolishes.
- **Kiro** is spec-driven development as a product feature — an excellent solo loop, no consensus.

The pattern holds across the whole landscape, not just the spec tools: each approach owns one piece of the puzzle — scenarios, constitutions, hooks, personas, decision provenance, intent gates, exposure control — and none combines consensus semantics, customer inclusion, persistent product truth, and calibrated agent autonomy. The partial implementations are witnesses that the space is real, not competitors: they prove the definition-and-delta core works, and they mark exactly where the unsolved half begins — the moment more than one human needs to agree.

Detailed comparison write-ups are planned as blog posts.
