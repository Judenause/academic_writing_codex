# Professor-Preferred Writing Rules

Use this checklist as the default revision lens.

## Core Principle

Treat a paper or dissertation as persuasive writing. The reader should understand why the problem matters, why existing approaches are insufficient, why the proposed idea follows naturally, and what evidence supports the conclusion.

## Paragraph Flow

Prefer paragraphs with a clear job:

1. Topic sentence that states the paragraph's role.
2. Concrete explanation or failure mode.
3. Gap or implication.
4. Transition to the next paragraph or method component.

Avoid paragraphs that merely list background facts, components, or results without showing why the sequence matters.

## Professor-Style Paragraph Test

Each paragraph must answer four questions:

1. What problem, claim, or transition is this paragraph responsible for?
2. What concrete mechanism, example, result, or citation supports the paragraph?
3. Why does this paragraph need to appear here rather than earlier or later?
4. Does the final sentence close the paragraph or prepare the next paragraph?

If any answer is unclear, revise the paragraph before polishing individual sentences.

## Sentence-Level Rules

- Keep sentences short enough to parse on first reading.
- Split sentences that contain multiple `which`, `that`, `where`, or nested modifier clauses.
- Replace vague pronouns when ambiguity is possible:
  - Weak: `This increases overhead.`
  - Better: `The additional routing logic increases overhead.`
- Keep `it`, `this`, `these`, and `they` only when the antecedent is the immediately preceding noun or concept.
- Prefer active, concrete verbs over nominalized phrases.
- Avoid em-dashes; use commas, parentheses, colons, or separate sentences.
- Avoid wording that sounds like generic AI prose: inflated adjectives, symmetrical filler, over-polished transitions, and broad claims without evidence.

## Evidence and Citation Rules

- Add or request citations for claims about prior work, limitations, trends, measured costs, benchmarks, datasets, and hardware constraints.
- Do not cite a paper without explaining why it is relevant.
- Do not stack citations as a substitute for synthesis.
- Never fabricate citation keys or bibliographic facts.
- If no source is available, mark the sentence with a precise citation need.

## Risky Claim Patterns

Flag claims containing these patterns for citation, scope, or evidence review:

- Priority or novelty: `first`, `novel`, `no prior work`, `unprecedented`, `state-of-the-art`.
- Deployment claims: `practical`, `real-time`, `hardware compatible`, `in-sensor deployable`, `sensor-scale`.
- Magnitude claims: `orders of magnitude`, `substantial`, `dominant`, `large`, `tight budget`.
- Proof-like verbs: `proves`, `confirms`, `demonstrates`, `ensures`, `guarantees`, `enables`.
- Broad quality claims: `robust`, `efficient`, `effective`, `scalable`, `generalizes`.

For each flagged claim, choose one action:

1. Attach or verify a citation.
2. Add the evaluation scope, baseline, and condition.
3. Soften the verb to match the evidence.
4. Mark the claim as needing a source.

## Preferred Claim Strength

- Use strong claims only when the text has direct evidence.
- Use measured language for scope boundaries: `under the evaluated conditions`, `within this implementation`, `relative to the fixed baseline`.
- Distinguish contribution from validation scope. Do not imply fabricated silicon, full-system implementation, or dataset coverage beyond the available evidence.

## Common Revisions

- Convert fact lists into causal chains.
- Move the limitation of prior work before the proposed method.
- Tie each contribution to a named problem or gap.
- State why a result matters, not only the numerical result.
- Keep transitions explicit between chapters, sections, and paragraphs.

## Preferred Before/After Patterns

Weak:
`This demonstrates that SISA is efficient.`

Better:
`The 11,800x energy reduction in the single-layer synthesis comparison indicates that SISA reduces dense-scan data movement under the evaluated 14 nm conditions.`

Weak:
`These methods are impractical for in-sensor deployment.`

Better:
`The additional routing fabric and scratchpad management make these accelerator-style methods difficult to absorb within the area budget of an image sensor front end.`

Weak:
`This solves the noise problem.`

Better:
`The temporal leakage stage suppresses isolated activations before spatial aggregation, reducing the noise patterns evaluated in the BNN backend.`
