# Revision Passes

Apply only the passes needed for the request. Default order when unspecified:

1. `advisor pass`
2. `flow pass`
3. `sentence pass`
4. `citation pass`

## `advisor pass`

Check whether the text reads like persuasive academic writing rather than a flat summary.

- Does each paragraph have a clear argumentative job?
- Does each section advance the thesis?
- Are the claims easy to defend in front of an advisor or committee?

## `flow pass`

Repair paragraph and section logic.

- Make paragraph roles explicit.
- Improve transitions between problem, limitation, method, and evidence.
- Remove repeated framing when it does not advance the argument.

## `sentence pass`

Improve readability without changing technical meaning.

- Split long or nested sentences.
- Replace ambiguous pronouns with explicit nouns.
- Prefer one evidence-sensitive claim per sentence.
- Remove AI-like polish and inflated transitions.

## `citation pass`

Audit whether each claim has the right evidence support.

- Add or request citations for prior work and factual claims.
- Mark unsupported claims precisely.
- Avoid citation stacking without synthesis.

## `defense pass`

Use when the text is likely to face committee or reviewer scrutiny.

- Soften unsupported strong verbs.
- Bound claims by implementation, dataset, baseline, and condition.
- Separate contribution claims from validation scope.

## `latex-safe pass`

Use when editing live LaTeX sources.

- Preserve equations, notation, labels, figure references, and citation keys.
- Avoid edits that can break macros or change technical numbers without evidence.
