# Mode Map

Choose the lightest ARS mode that matches the request.

## `ars-plan`

Use for guided paper planning, chapter sequencing, contribution framing, or outline construction.

- Inputs: topic, venue, contribution idea, existing notes, target structure
- Default output: chapter plan, section outline, open-question list
- Upstream source: `commands/ars-plan.md`

## `ars-lit-review`

Use for a literature-review style writeup, annotated synthesis, or source-backed related-work drafting.

- Inputs: topic, source list, search results, claim focus
- Default output: literature review section or annotated synthesis
- Upstream source: `commands/ars-lit-review.md`

## `ars-outline`

Use for evidence-aware outline building without drafting the full paper.

- Inputs: topic, thesis, target paper structure, evidence inventory
- Default output: detailed outline with evidence map
- Upstream source: `commands/ars-outline.md`

## `ars-abstract`

Use for abstract-only generation once the contribution, method, and findings are already defined.

- Inputs: paper summary, method, results, keywords, target language constraints
- Default output: abstract draft and keyword set
- Upstream source: `commands/ars-abstract.md`

## `ars-revision`

Use for draft revision after peer review, advisor feedback, or internal comments.

- Inputs: current draft, reviewer comments, target venue, nonnegotiable constraints
- Default output: revised draft text and response-to-reviewers structure when needed
- Upstream source: `commands/ars-revision.md`

## `ars-revision-coach`

Use when reviewer comments need to be parsed into an action plan before any rewriting starts.

- Inputs: reviewer comments, editor decision, current draft status, venue expectations
- Default output: revision roadmap and response-letter skeleton
- Upstream source: `commands/ars-revision-coach.md`

## `ars-citation-check`

Use for reference integrity audits.

- Inputs: draft text, bibliography, target citation style
- Default output: citation error report covering missing support, mismatches, and formatting issues
- Upstream source: `commands/ars-citation-check.md`

## `ars-format-convert`

Use for format and citation-style conversion work once the content itself is stable.

- Inputs: draft format, target format, citation style, bibliography assets
- Default output: conversion plan or converted output, depending on available files and toolchain
- Upstream source: `commands/ars-format-convert.md`

## `ars-disclosure`

Use for venue-specific AI usage disclosure statements.

- Inputs: target venue, actual AI assistance used, disclosure constraints
- Default output: disclosure statement draft
- Upstream source: `commands/ars-disclosure.md`

## `ars-full`

Use only when the user actually wants staged orchestration from research through writing, review, revision, and finalization.

- Inputs: topic or draft plus stage status
- Default output: staged workflow progress with explicit human checkpoints
- Upstream source: `commands/ars-full.md`

## Closest-mode fallback

- Abstract writing: use `ars-abstract` when the paper state is already known, otherwise start with `ars-plan`.
- Reviewer response coaching: use `ars-revision-coach` before `ars-revision` when comments are messy or contradictory.
- Format conversion preparation: use `ars-format-convert`, often after `ars-citation-check`.
- Methodology or quality critique of an existing paper: usually start from `ars-citation-check` plus review-style findings, unless the user clearly asks for the full pipeline.
