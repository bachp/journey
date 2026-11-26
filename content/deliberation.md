+++
title = "Deliberation"
description = "The half a data model cannot carry: two gates, per-role consensus, evidence, and a ceremony that scales with risk — not with gate count."
weight = 2
+++

A journey is not a work item to be disposed of. It is a deliberation with a return: the intent states the goal, the exploration forms agreement, the return folds the deltas into the definition. Everything on [the model page](/methodology/) describes what a journey *carries*; this page describes how it *earns* the right to carry it.

## Two gates, and only two

- **The intent gate.** Stakeholders agree on what the journey is trying to achieve and why, in prose. It is cheap to cross, and the intent is relatively stable from there on: its post-gate job is to be cited, not edited.
- **The behavior gate.** Stakeholders agree on observable outcomes — "when I click X, I see Y" — stated as stakeholder-legible scenarios and backed by verification: tests, analyzers, demonstrated behavior at production-grade fidelity. A customer who approved a mockup approved a mockup. This is the gate to completion.

Everything between the gates is iteration space, and it is deliberately the largest part of the journey. That is where the artifact climbs the fidelity ladder and where stakeholders discover what they actually think.

## Consensus is per gate, per role, and not unanimity

A gate passes when its assent rule is met, not when every participant actively agrees. What unanimity would cost in coordination, the methodology pays instead in **objection rights**: each role holds a veto exactly where its accountability lives, and raising a role's autonomy never removes its veto. That is what keeps "not unanimous" from becoming "nobody was asked."

An example role set — implementations vary, and so do the roles:

| Role | Intent gate | Behavior gate |
|---|---|---|
| Architect | Explicit sign-off; holds veto | Veto only, on structural coherence |
| Product owner | Explicit sign-off, representing the customer | Sign-off, or delegated to a proxy via an autonomy dial |
| Tester (risk holder) | Explicit sign-off | Sign-off on scenario executability; may be delegated |
| Customer | Represented by the product owner — no direct vote | **Behavioral assent with a veto window**: positive usage evidence from the named personas, or explicit assent; a negative signal inside the window reopens the gate |

The customer is deliberately not a gate stakeholder at the intent gate: there is nothing to react to before an artifact exists, and requiring direct customer agreement there would block everything. On the behavior side the customer participates **through the product**, not through the protocol. Agreement is persona-scoped: the named customer-side roles each need behavioral evidence of successful use, or explicit assent. Aggregate telemetry is a supplementary signal, and becomes primary only where the customer genuinely is a population.

## Evidence admits each gate

What a gate demands is not fixed. The intent gate selects the evidence disciplines for the whole journey — problem and outcome evidence always, plus domain-model, architecture, environment, non-functional, safety, or operational evidence where the risk or the obligations the change touches call for them. These disciplines are lenses, not phases: they attach to the gates that need them, several may bind the same gate, and nothing sequences them. Missing selected evidence blocks the gate. It is never crossed provisionally and back-filled later.

## Gates reopen, but never on stale authority

A passed gate reopens only on new evidence that changes the basis on which it passed — the intent falsified, an assumption broken, an obligation changed, an approved behavior demonstrably failing. Neither elapsed time nor upstream churn alone reopens anything. And reopening is always scoped to the delta the new evidence implicates, so a journey resumes at the state that delta touches, not from zero.

A gate that genuinely cannot pass does not linger. It moves to `blocked` with the conflict recorded, and escalates to the role accountable for the tension — the architect for structural conflicts, the product owner for value conflicts. Escalation resolves the *decision* — reverse a veto, split the journey, reject it — never the meaning of agreement, and the dissent is preserved in the record.

## Two independent axes: type and risk

**Type is what the journey publishes.** The highest-governing deliverable decides, in the order `feature > decision > refactoring > trivial`.

| Type | Path | Publishes |
|---|---|---|
| **Feature** | full | Code plus a scenario suite, which joins the definition's behavior projection |
| **Decision** | abbreviated | An ADR — the frozen, formatted excerpt of the agreement |
| **Refactoring** | abbreviated | Code plus no-change verification evidence |
| **Trivial** | short lane | Code |

The type names the path, not the artifact list: a feature journey can also emit an ADR. And an ADR is what a decision-bearing journey emits — not a parallel process. A record that no journey agreed to is a proposal with good formatting.

**Risk is what is at stake.** Every journey carries a risk class — low, elevated, high — assessed at incubation exit against what is at stake (safety, security, privacy, compliance, operational continuity), how reversible a wrong outcome is, who is exposed, and how much uncertainty remains. The assessment is evidence, not intuition: it names the dimensions that drove the class and is recorded with the intent, so the class is auditable and re-derivable.

The risk class governs ceremony independently of type. It raises the evidence floor and decides who must provide it; it adds roles to gates the type alone would not require; it caps how far autonomy may substitute for a human decision; it sets how strong customer evidence must be.

Two rules keep the cheap lanes from becoming the place where risk hides:

- **Unclear risk is high risk** until evidence resolves it — harsh on purpose, so that "we didn't look" is the most expensive option.
- **Reclassification is evidence-triggered and auditable.** A behavior delta in a "refactoring", a compliance dimension in a "copy fix": the journey escalates out of its lane, because the lane was rented by the risk class, not owned by the type.

Ceremony scales with evidence and risk — never with gate count. A high-risk trivial journey is not a contradiction; it is the system working.

## States

```
incubating → idea → agreed → verified → accepted → merged
```

`blocked` means a gate cannot pass *yet*: a dependency, a missing capability, an unresolved external decision. The agreement stands, the journey resumes when the blocker clears, and `blocked` carries no stigma. `rejected`, `split`, `merged_into`, and `archived` are terminal, with the rationale preserved in the record.

Gates must be able to say "not now" without forcing "no", or every dependency wait becomes a premature funeral. Reopening a rejected journey is not a state transition: it is a new journey that cites the old one's record.

## The return

At the return, both outputs are produced at once: the deltas fold into the definition, and the journey freezes into its record. A decision that clears the ADR bar — hard to reverse, surprising without context, the result of a real trade-off — is promoted out of the record into the repository, because it stays useful after its record is superseded.

**Return is the full act; merge is the mechanic it culminates in.** The two are never used interchangeably.

The invariants that make all of this testable are on [Invariants](/invariants/).
