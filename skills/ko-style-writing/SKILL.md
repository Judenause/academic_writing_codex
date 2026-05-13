---
name: ko-style-writing
description: Advisor-preferred academic writing and revision for persuasive, reader-friendly English research prose. Use when writing or revising dissertation chapters, paper abstracts, introductions, related work, contribution paragraphs, conclusions, advisor-facing drafts, LaTeX academic prose, or citation-sensitive technical claims where the user wants clear argument flow, non-AI-like wording, unambiguous references, and evidence-backed claims.
---

# Ko Style Writing

## Overview

Revise academic prose as persuasive technical writing, not as a neutral list of facts. Prioritize reader comprehension, logical flow, explicit antecedents, short sentence structure, and citation integrity.

## Required References

- Read `references/professor-preferences.md` before substantial writing or revision.
- Read `references/revision-passes.md` when the user asks to check, revise, polish, review, or improve prose.
- Read `references/model-paper-patterns.md` when drafting abstracts, introductions, related work, contributions, or conclusions.
- In the dissertation repo, also read `context.md` and `writing_checklist.md`; those local rules override this skill when they are more specific.

## Workflow

1. Identify the argumentative role of the target text: motivation, problem, limitation, gap, method, result, implication, or transition.
2. Select revision passes from `references/revision-passes.md`. If the user does not specify a pass, apply `advisor pass`, `flow pass`, `sentence pass`, and `citation pass` in that order.
3. Check whether each paragraph persuades the reader through a chain of reasoning: context -> problem -> why existing approaches fall short -> proposed idea -> evidence.
4. Revise for reader clarity:
   - Replace ambiguous `it`, `this`, `these`, and `they` with explicit nouns when the antecedent is not unmistakable.
   - Split long sentences, especially sentences with multiple relative clauses.
   - Keep one technical claim per sentence when the claim needs evidence.
   - Preserve precise terminology and notation from the active project.
5. Revise for advisor-preferred academic tone:
   - Avoid AI-like polish, inflated adjectives, em-dashes, and decorative transitions.
   - Prefer concrete verbs and measured claims.
   - Use hedging only when the evidence requires it.
6. Audit citation integrity:
   - Attach citations to claims that need prior-work support, measured evidence, or factual grounding.
   - Never invent references, results, baselines, datasets, or citation keys.
   - If evidence is missing, mark the exact claim as needing a source instead of silently strengthening or weakening it.
7. For advisor-facing dissertation work, check whether the revised text would satisfy a professor reading for argument quality:
   - The section should not read as a list of paper results.
   - Each paragraph should make the next paragraph feel necessary.
   - Technical claims should be bounded by the actual validation evidence.
   - The contribution should be easy to defend against committee questions.
8. Return the revised text plus a short note only when useful: what changed, unresolved citation needs, and any claims whose strength still depends on missing evidence.

## Dissertation-Specific Rules

When working in `/local_data/phd`, preserve the local dissertation style:

- Use `$E_{\text{thr}}$` and `$T_{\text{exp}}$`; do not introduce `$V_{\text{thr}}$`.
- Use `Spatially-Indexed Sparsity-Aware` for SISA.
- Use LaTeX citation commands such as `~\cite{key}` instead of raw numeric citation text.
- Avoid em-dashes and unsupported strong claims.
- Do not rewrite technical numbers, equations, labels, figure references, or citation keys unless the user asks or the source clearly requires it.

## Output Modes

- For direct rewrite requests, edit the file when the user asks for implementation.
- For review requests, lead with issues ordered by severity and cite file/line references.
- For uncertain claims, provide a focused citation-needed list rather than broad commentary.
- For broad "check this chapter/section" requests, perform a conservative file edit only when the issues are local and low-risk; otherwise report prioritized findings first.
- When the user says the professor must be satisfied, treat the request as advisor-facing revision: improve argument flow, remove unsupported or repetitive claims, and flag committee-risk points before doing sentence polish.
