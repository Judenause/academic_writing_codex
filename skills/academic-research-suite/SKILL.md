---
name: academic-research-suite
description: Human-in-the-loop academic research and paper workflow for Codex. Use when planning a paper, building a literature review, revising from reviewer comments, checking citation integrity, or running a research-to-publication workflow with explicit checkpoints and noncommercial academic-use guardrails.
---

# Academic Research Suite

## Overview

This skill adapts upstream ARS workflow content into a Codex-native surface. Treat it as an academic copilot, not an autonomous paper author.

- Keep the human researcher responsible for research questions, methods, interpretation, and final claims.
- Prefer explicit checkpoints over silent end-to-end automation.
- Do not invent sources, results, reviewer feedback, datasets, or venue requirements.
- Treat the upstream ARS repository as the detailed source of truth when a mode needs deeper procedural rules.

## Required References

- Read `references/guardrails.md` before substantial use.
- Read `references/modes.md` to choose the right ARS mode.
- Read `references/source-map.md` when you need to open the upstream ARS materials directly.

## Activation

Use this skill when the user asks for any of the following:

- paper planning through guided questioning
- literature review generation or synthesis
- draft revision from reviewer comments
- citation checking or format-conversion prep
- end-to-end research or paper workflow with explicit checkpoints
- ARS or `ars-*` mode behavior inside Codex

## Workflow

1. Identify the requested mode from the user intent. If unclear, map it using `references/modes.md`.
2. Confirm the available inputs: topic, draft, outline, citations, reviewer comments, target venue, or formatting target.
3. Apply the matching mode contract:
   - `ars-plan`: Socratic planning for chapter or section structure.
   - `ars-lit-review`: literature-review style synthesis from provided or gathered sources.
   - `ars-outline`: build a detailed outline and evidence map without drafting the full paper.
   - `ars-abstract`: produce an abstract and keywords from an already defined paper state.
   - `ars-revision`: revise a draft against reviewer feedback and produce an R&R style response when needed.
   - `ars-revision-coach`: turn reviewer comments into a roadmap before rewriting.
   - `ars-citation-check`: audit missing, mismatched, weak, or malformed citations.
   - `ars-format-convert`: convert draft format or citation style.
   - `ars-disclosure`: draft venue-specific AI usage disclosure text.
   - `ars-full`: orchestrate a staged research-to-publication flow with explicit human checkpoints.
4. Keep the human in the loop:
   - surface assumptions and missing evidence
   - stop at meaningful checkpoints before making stronger claims
   - distinguish verified facts from suggested prose or workflow scaffolding
5. When the task depends on the upstream ARS methodology or terminology, open only the directly relevant upstream file from `references/source-map.md` instead of loading the whole repository.
6. Return the main artifact the mode is supposed to produce, plus only the most relevant warnings or unresolved evidence gaps.

## Codex-Specific Adaptation

- The upstream Claude distribution exposes many separate commands. In Codex, treat this as one umbrella skill with `ars-*` mode aliases.
- If the user explicitly types `$academic-research-suite`, activate this skill and choose the closest mode from context.
- If the user names an `ars-*` mode in plain text, use that mode behavior through this skill even though Codex does not expose slash commands here.
- Prefer concise artifacts and direct edits over ceremony unless the user explicitly wants the full ARS process.

## Output Rules

- For planning requests, produce a structured plan, outline, or question sequence.
- For review or revision requests, lead with issues, gaps, or edits that materially affect acceptance quality.
- For citation checks, produce a concrete audit list tied to exact claims or references.
- For full-pipeline requests, make stage boundaries explicit and do not pretend the whole pipeline is complete without evidence.

## Boundaries

- Noncommercial academic-use guardrails apply because the upstream source is CC BY-NC 4.0.
- This skill is a Codex packaging layer, not a verbatim copy of the upstream plugin system.
- If a user needs exact upstream command semantics, open the mapped source file from the vendored ARS checkout or from the upstream repository.
