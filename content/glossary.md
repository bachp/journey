+++
title = "Glossary"
description = "Every term the methodology uses, defined once and linked to where it is developed — including the vocabulary it retired."
weight = 5
+++

The methodology has a small vocabulary and uses it strictly. Terms are grouped, not alphabetical: each group is a place where a conversation tends to stall.

## Artifacts and the definition

<dl class="glossary">
<dt id="product-definition">Product Definition</dt>
<dd>The sum of all Maintained Artifacts. The product <em>is</em> its definition. Meta Artifacts frame it but are not part of it. <a href="/methodology/#four-regimes-not-one">Developed here</a>.</dd>

<dt id="maintained-artifact">Maintained Artifact</dt>
<dd>An artifact that tells you what the product is now, kept current in place through explicit change: charter, requirements, specifications, acceptance criteria, tests, code.</dd>

<dt id="provenance-artifact">Provenance Artifact</dt>
<dd>An artifact that tells you why the product looks like this. Never edited — a later change replaces it. Intents, plans, test results, investigations, reviews, records.</dd>

<dt id="derived-artifact">Derived Artifact</dt>
<dd>An artifact rebuilt from the definition: build outputs, binaries, generated code. No gate owns a derived artifact.</dd>

<dt id="meta-artifact">Meta Artifact</dt>
<dd>An artifact that sets the rules by which the repository applies the methodology — the journey registry, the confidence dial. Versioned and edited in place; the commit message is its record.</dd>

<dt id="regeneration-confidence">Regeneration confidence</dt>
<dd>Your trust that rebuilding gives the same artifact again. It — not the artifact's kind — decides its type. Distrust the compiler and the binary joins the definition; trust the agent and its specification and the code becomes derived. The <strong>confidence dial</strong> is the Meta Artifact that records this per artifact class.</dd>

<dt id="snapshot">Product Definition Snapshot</dt>
<dd>A frozen copy of the definition. A Snapshot is itself a Provenance Artifact: it explains one moment, and is never edited to track the product forward.</dd>
</dl>

## The journey

<dl class="glossary">
<dt id="journey">Journey</dt>
<dd>A change to the product, driven by an Intent. It carries deltas to any Maintained Artifact plus the provenance behind them, and at its end it becomes its Journey Record. <a href="/methodology/#the-axiom">Developed here</a>.</dd>

<dt id="intent">Intent</dt>
<dd>The goal of a change. Living during exploration — the journey's current understanding, readable by a newcomer — and cited rather than edited once the intent gate has passed.</dd>

<dt id="delta">Delta</dt>
<dd>A change to one Maintained Artifact. A journey carries deltas, and the return folds them into the definition.</dd>

<dt id="journey-record">Journey Record</dt>
<dd>The frozen journey: intent, decisions, evidence, outcome. It explains the definition and never governs it.</dd>

<dt id="return">Return</dt>
<dd>The full act that ends a journey: the deltas fold into the Product Definition <em>and</em> the journey freezes into its record, both outputs produced at once. <strong>Merge is the mechanic the return culminates in</strong> — the two are never interchangeable.</dd>

<dt id="trivial-lane">Trivial lane</dt>
<dd>The short path for changes with no new observable behavior — typo fixes, config tweaks, copy edits. It bypasses the intent gate and still verifies behavior. Eligibility is a risk judgement: evidence found inside the lane reclassifies the journey.</dd>
</dl>

## Agreement

<dl class="glossary">
<dt id="intent-gate">Intent gate</dt>
<dd>The first of the two gates: stakeholders agree on what the journey is trying to achieve and why, in prose. Cheap to cross; the agreement is stable from there on. <a href="/deliberation/#two-gates-and-only-two">Developed here</a>.</dd>

<dt id="behavior-gate">Behavior gate</dt>
<dd>The second gate: stakeholders agree on observable outcomes — "when I do X, I see Y" — backed by tests, analyzers, or demonstrated behavior at production-grade fidelity. It is the gate to completion.</dd>

<dt id="objection-right">Objection right</dt>
<dd>A role's veto, held exactly where its accountability lives — the architect on structure, the tester on executability, the customer on observed behavior. Consensus is per gate and per role and is <em>not</em> unanimity; objection rights are what keep "not unanimous" from meaning "nobody was asked".</dd>

<dt id="autonomy-dial">Autonomy dial</dt>
<dd>How far an agent proxy may decide on a role's behalf, including a customer's behavioral assent. Raising autonomy never removes the underlying veto.</dd>

<dt id="blocked">Blocked</dt>
<dd>A gate that cannot pass <em>yet</em>: a dependency, a missing capability, an unresolved external decision. The agreement stands and the journey resumes; it carries no stigma. Gates must be able to say "not now" without forcing "no".</dd>

<dt id="rejected">Rejected</dt>
<dd>A terminal state with the rationale preserved in the record. Reopening is not a state transition — it is a new journey that cites the old one's record.</dd>

<dt id="gate-reopening">Reopening a gate</dt>
<dd>Allowed only on new evidence that changes the basis on which the gate passed — intent falsified, assumption broken, approved behavior failing — and scoped to the delta that evidence implicates. Elapsed time and upstream churn reopen nothing.</dd>
</dl>

## Type and risk

<dl class="glossary">
<dt id="journey-type">Journey type</dt>
<dd>What the journey publishes, in the order <code>feature &gt; decision &gt; refactoring &gt; trivial</code>. The type names the path, not the artifact list: a feature journey can also emit an ADR. <a href="/deliberation/#two-independent-axes-type-and-risk">Developed here</a>.</dd>

<dt id="risk-class">Risk class</dt>
<dd><code>low</code>, <code>elevated</code>, <code>high</code> — what is at stake, assessed against safety, security, privacy, compliance, continuity, reversibility, exposure, and residual uncertainty. It sets the evidence floor, the roles in the gates, and how far autonomy may substitute for a human decision. Unclear risk is high risk until evidence resolves it.</dd>

<dt id="adr">Architecture decision record (ADR)</dt>
<dd>The frozen excerpt of an agreement, promoted out of a journey record for decisions that are hard to reverse, surprising without context, and the result of a real trade-off. An ADR is something a journey emits, not a parallel process.</dd>
</dl>

## Implementation

<dl class="glossary">
<dt id="invariant">Invariant</dt>
<dd>One of the three things any conforming implementation must provide — both projections, both regimes, deltas plus provenance. <a href="/invariants/">The conformance test</a>.</dd>

<dt id="journey-registry">Journey registry</dt>
<dd>The Meta Artifact that lists journeys in flight and records their state. Where it lives is an implementation choice: a forge tracker, or a <code>journeys/</code> directory.</dd>

<dt id="registry-adapter">Registry adapter</dt>
<dd>The binding that maps the abstract artifact classes onto concrete homes — which artifacts live in git, which in a tracker, and where a journey's provenance survives after its record freezes. The choice binds new journeys only; frozen records stay where they froze.</dd>
</dl>

## Retired vocabulary

Earlier writing — including this site's own blog posts — uses terms the methodology has since dropped. If you are reading something that uses them, this is the mapping.

<dl class="glossary">
<dt id="retired-baseline">baseline</dt>
<dd>Retired in favour of <strong>Product Definition</strong>. The old term described the same object but suggested a floor rather than a body of knowledge. <a href="#product-definition">See Product Definition</a>.</dd>

<dt id="retired-keystone">keystone</dt>
<dd>Retired as ambiguous: it was used for both the consensus axiom and the regeneration-confidence bet. Use <strong>the axiom</strong> for "consensus binds to intent and observable behavior" and <strong>regeneration confidence</strong> for the dial.</dd>

<dt id="retired-two-classes">two classes</dt>
<dd>The coarse split — living definition that governs, frozen record that explains — remains true, but the canonical taxonomy is the <a href="#product-definition">four artifact types</a>: Maintained, Provenance, Derived, Meta.</dd>
</dl>
