# Ko Style Writing for Codex

[한국어 README](README.ko.md)

This skill packages a persuasive academic writing workflow for Codex. It is tuned for reader-friendly English research prose, conservative claim handling, and citation-aware revision.

## What it does

- revises academic prose for argument flow rather than summary-only narration
- improves sentence clarity and explicit antecedents
- checks whether claims are supported and appropriately scoped
- stays safe for live LaTeX editing

## What it does not do

- it does not invent citations, results, datasets, or novelty claims
- it does not justify stronger claims than the evidence supports
- it does not replace advisor review

## Install

### Option 1: Copy the skill

```bash
mkdir -p ~/.codex/skills
cp -R skills/ko-style-writing ~/.codex/skills/
```

### Option 2: Symlink for active development

```bash
mkdir -p ~/.codex/skills
ln -s "$(pwd)/skills/ko-style-writing" ~/.codex/skills/ko-style-writing
```

## Main files

- `skills/ko-style-writing/SKILL.md`
- `skills/ko-style-writing/references/professor-preferences.md`
- `skills/ko-style-writing/references/model-paper-patterns.md`
- `skills/ko-style-writing/references/revision-passes.md`

## Example prompts

```text
$ko-style-writing Revise this introduction so it reads like a persuasive argument
$ko-style-writing Check this chapter for claim strength and citation gaps
$ko-style-writing Apply a flow pass and sentence pass to this LaTeX section
$ko-style-writing Rewrite this contribution paragraph without AI-like wording
```

## Revision passes

- `advisor pass`: checks persuasion quality and committee defensibility
- `flow pass`: repairs paragraph and section logic
- `sentence pass`: improves readability and explicitness
- `citation pass`: audits evidence support
- `defense pass`: tightens claim scope under scrutiny
- `latex-safe pass`: preserves LaTeX-sensitive structures

## Dissertation-specific behavior

When used inside the dissertation repo, the skill preserves local notation and citation conventions, including:

- `$E_{\text{thr}}$` and `$T_{\text{exp}}$`
- `Spatially-Indexed Sparsity-Aware` for SISA
- LaTeX citation keys such as `~\cite{key}`

## Public note

This public README intentionally omits personal-name branding. The skill is described in functional terms so it can be shared without exposing advisor identity in the repository landing page.
