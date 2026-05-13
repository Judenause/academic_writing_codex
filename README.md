# Academic Research Skills for Codex

Codex-native port of [`Imbad0202/academic-research-skills`](https://github.com/Imbad0202/academic-research-skills).

This repository shape is a **sibling distribution** of the upstream ARS project. It keeps the same human-in-the-loop philosophy, the same noncommercial license boundary, and the same `ars-*` workflow vocabulary, but adapts the outer packaging to Codex as a single umbrella skill: `$academic-research-suite`.

## What this port is

- A Codex packaging layer for the upstream ARS workflow content
- A single-skill adapter that maps `ars-*` requests into Codex-friendly mode selection
- A documentation-first wrapper that points back to the upstream ARS tree for deeper procedural detail

## What this port is not

- Not an official upstream distribution unless the upstream maintainer adopts it
- Not a verbatim clone of Claude Code plugin packaging
- Not a promise of identical agent behavior across Claude and Codex

## Upstream source

- Upstream repo: `https://github.com/Imbad0202/academic-research-skills`
- Upstream pinned commit: `235e3760e59da961c31b67409e5ceb79a1e6e524`
- Port shape: sibling distribution

The upstream README explicitly mentions a Codex sibling distribution model and describes it as "same workflow content, Codex-native packaging as a single `$academic-research-suite` skill with `ars-*` aliases." This port follows that contract.

## Skill entrypoint

Repository skill path:

- `skills/academic-research-suite/SKILL.md`

Suggested installed path on a local Codex setup:

- `~/.codex/skills/academic-research-suite/SKILL.md`

Core references:

- `skills/academic-research-suite/references/guardrails.md`
- `skills/academic-research-suite/references/modes.md`
- `skills/academic-research-suite/references/source-map.md`

## Mode mapping

The Codex port exposes the following upstream-style aliases through one skill:

| Alias | Purpose | Typical output |
| --- | --- | --- |
| `ars-plan` | Socratic paper or chapter planning | outline, section plan, open questions |
| `ars-lit-review` | literature review synthesis | related-work draft, annotated synthesis |
| `ars-outline` | outline without full drafting | evidence-aware outline |
| `ars-abstract` | abstract-only drafting | abstract plus keywords |
| `ars-revision` | revise draft from comments | revised text plus response structure |
| `ars-revision-coach` | parse review comments before rewriting | roadmap plus response-letter skeleton |
| `ars-citation-check` | citation integrity audit | error list, missing-support list |
| `ars-format-convert` | format or style conversion | conversion plan or converted artifact |
| `ars-disclosure` | AI-use disclosure statement | venue-specific disclosure text |
| `ars-full` | staged end-to-end workflow | checkpointed pipeline progression |

## Usage examples

See [examples/USAGE_EXAMPLES.md](examples/USAGE_EXAMPLES.md) for the full prompt catalog.

Quick examples:

```text
$academic-research-suite 논문 아웃라인 같이 잡아줘
ars-plan mode로 "edge AI for event cameras" 논문 구조 짜줘
ars-lit-review 방식으로 event-based vision related work 초안 만들어줘
ars-revision-coach처럼 reviewer comment를 revision roadmap으로 바꿔줘
ars-citation-check처럼 이 section citation 문제만 잡아줘
ars-full처럼 지금 초안 기준으로 어느 stage부터 시작해야 할지 판단해줘
```

## Porting rationale

Why the Codex port uses one umbrella skill instead of many slash commands:

- Codex skill activation is more natural when the workflow lives behind one explicit skill surface.
- The upstream Claude packaging uses many small command wrappers; Codex does not need that extra layer.
- Keeping the port thin reduces drift and makes sync with upstream easier.

## Update policy

- Track upstream ARS minor releases on an approximately 6-week cadence
- Update the pinned upstream commit in `manifest.json` when syncing
- Keep mode names aligned with upstream `commands/ars-*.md`
- Keep this README honest about divergence between Claude and Codex behavior

## Model portability note

Upstream ARS is calibrated for Claude Code, with model choices such as Opus for architecture or review depth and Sonnet for execution. This port preserves the workflow intent and mode boundaries, but Codex may differ in:

- skill activation and routing
- subagent behavior
- tool availability
- prompt length tolerance
- exact output tone and checkpoint behavior

Document those differences when publishing examples or bug reports.

## Publishing this to GitHub

Minimal sibling-distribution checklist from the upstream contribution policy:

1. Keep the upstream commit pinned in `manifest.json`.
2. Name a maintainer in this README.
3. Document the sync policy.
4. Document model-portability differences.
5. Include at least one end-to-end example artifact set under `examples/`.

## License note

The upstream ARS project is source-available under CC BY-NC 4.0. This port should preserve that noncommercial boundary and clearly attribute the upstream project.
