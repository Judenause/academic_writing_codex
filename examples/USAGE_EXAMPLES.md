# Usage Examples

This file documents the full user-facing example surface for the Codex port of ARS.

## 1. Main skill activation

```text
$academic-research-suite 논문 구조 같이 잡아줘
$academic-research-suite I need help planning a conference paper on event-based vision
$academic-research-suite reviewer comment를 반영한 수정 전략부터 세워줘
```

## 2. `ars-plan`

Use for guided planning before drafting.

```text
ars-plan mode로 "event-driven object detection" 논문 아웃라인 짜줘
ars-plan처럼 내 contribution 3개를 IMRaD 구조에 배치해줘
ars-plan 방식으로 chapter-by-chapter 질문을 해가며 구성 잡아줘
```

## 3. `ars-lit-review`

Use for literature-review style synthesis.

```text
ars-lit-review 방식으로 neuromorphic vision related work 초안 만들어줘
ars-lit-review처럼 이 12편 논문을 thematic review로 묶어줘
ars-lit-review mode로 source-backed related work paragraph를 써줘
```

## 4. `ars-outline`

Use when the structure matters more than full prose.

```text
ars-outline처럼 full draft 말고 evidence map 있는 detailed outline만 만들어줘
ars-outline mode로 각 section마다 어떤 evidence가 들어가야 하는지 표시해줘
ars-outline 방식으로 rebuttal-ready outline을 먼저 잡아줘
```

## 5. `ars-abstract`

Use for abstract-only drafting after the paper state is known.

```text
ars-abstract처럼 abstract만 써줘
ars-abstract mode로 contribution, method, result를 바탕으로 keyword까지 정리해줘
ars-abstract 방식으로 짧은 conference abstract와 keywords를 만들어줘
```

## 6. `ars-revision`

Use for real revision work.

```text
ars-revision처럼 reviewer comment를 반영해서 draft를 고쳐줘
ars-revision mode로 수정된 문단과 response-to-reviewers 초안을 같이 줘
ars-revision 방식으로 overclaim 줄이고 rebuttal도 준비해줘
```

## 7. `ars-revision-coach`

Use before rewriting when comments are messy.

```text
ars-revision-coach처럼 이 review comments를 revision roadmap으로 정리해줘
ars-revision-coach mode로 어떤 코멘트를 먼저 처리해야 할지 우선순위 잡아줘
ars-revision-coach 방식으로 response letter skeleton만 먼저 만들어줘
```

## 8. `ars-citation-check`

Use for citation integrity and support audits.

```text
ars-citation-check처럼 이 section의 citation 문제를 다 찾아줘
ars-citation-check mode로 unsupported claim이 어디 있는지 표시해줘
ars-citation-check 방식으로 bib과 본문 citation mismatch만 점검해줘
```

## 9. `ars-format-convert`

Use when format or citation style conversion is the main task.

```text
ars-format-convert처럼 Markdown 초안을 LaTeX 구조로 바꿔줘
ars-format-convert mode로 citation style을 APA에서 IEEE로 바꿔줘
ars-format-convert 방식으로 DOCX 제출본 준비 절차를 정리해줘
```

## 10. `ars-disclosure`

Use for AI-use transparency statements.

```text
ars-disclosure처럼 NeurIPS용 AI usage disclosure 문구 만들어줘
ars-disclosure mode로 내가 사용한 AI assistance를 Nature 스타일로 정리해줘
ars-disclosure 방식으로 venue-specific disclosure 초안만 써줘
```

## 11. `ars-full`

Use when the user wants staged orchestration, not just one artifact.

```text
ars-full처럼 research부터 writing, review, revision까지 stage로 나눠서 진행해줘
ars-full mode로 지금 draft 상태를 보고 어느 stage부터 시작할지 판단해줘
ars-full 방식으로 explicit checkpoint 있는 end-to-end workflow를 운영해줘
```

## 12. Natural-language prompts without alias

The Codex port can still map plain requests to the nearest mode.

```text
논문 related work를 source-backed하게 정리해줘
리뷰어 코멘트를 revision roadmap으로 먼저 바꿔줘
이 draft에서 citation이 약한 문장을 전부 찾아줘
이 논문을 어떤 구조로 써야 할지 질문하면서 같이 잡아줘
```

## 13. GitHub README phrasing examples

Use these when describing the port publicly.

```text
This repository is a Codex-native port of Imbad0202/academic-research-skills.
It preserves the upstream ARS workflow vocabulary and human-in-the-loop philosophy, while adapting packaging to a single Codex skill named $academic-research-suite.
The upstream ARS repository remains the source of truth for workflow content; this repo provides the Codex adapter layer, mode mapping, and port-specific documentation.
```
