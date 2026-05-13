# Codex용 Academic Research Skills

[English README](README.md)

[`Imbad0202/academic-research-skills`](https://github.com/Imbad0202/academic-research-skills)의 Codex용 포트입니다.

이 저장소는 upstream ARS 프로젝트의 **sibling distribution** 형태를 따릅니다. 즉, human-in-the-loop 철학, 비상업적 라이선스 경계, `ars-*` 워크플로 어휘는 유지하되, 바깥 패키징만 Codex에 맞게 단일 우산 스킬 `$academic-research-suite` 형태로 조정한 포트입니다.

## 이 포트가 하는 일

- upstream ARS 워크플로를 Codex에서 쓰기 좋게 감싼 패키징 레이어
- `ars-*` 요청을 Codex 친화적인 mode 선택으로 연결하는 단일 스킬 어댑터
- 더 깊은 절차 규칙은 upstream ARS 쪽으로 다시 연결하는 문서 중심 래퍼

## 이 포트가 아닌 것

- upstream maintainer가 채택하기 전까지는 공식 upstream 배포판이 아님
- Claude Code 플러그인 패키징을 그대로 복제한 저장소가 아님
- Claude와 Codex에서 에이전트 동작이 완전히 동일하다는 보장이 아님

## Upstream source

- upstream repo: `https://github.com/Imbad0202/academic-research-skills`
- 고정 upstream commit: `235e3760e59da961c31b67409e5ceb79a1e6e524`
- 포트 형태: sibling distribution

upstream README에는 Codex sibling distribution이 명시되어 있고, "same workflow content, Codex-native packaging as a single `$academic-research-suite` skill with `ars-*` aliases"라고 설명되어 있습니다. 이 포트는 그 계약을 따릅니다.

## 설치 방법

이 저장소를 clone한 뒤, 스킬 디렉터리를 로컬 Codex skills 경로에 설치하면 됩니다.

### 방법 1: 스킬 복사

```bash
mkdir -p ~/.codex/skills
cp -R skills/academic-research-suite ~/.codex/skills/
```

### 방법 2: 개발용 심볼릭 링크

```bash
mkdir -p ~/.codex/skills
ln -s "$(pwd)/skills/academic-research-suite" ~/.codex/skills/academic-research-suite
```

### 확인

설치 후에는 Codex에서 아래처럼 호출하면 됩니다.

```text
$academic-research-suite Help me plan a paper on event-based vision
Use ars-citation-check mode on this draft section
```

## Skill entrypoint

저장소 내부 스킬 경로:

- `skills/academic-research-suite/SKILL.md`

로컬 Codex 환경에 설치했을 때 권장 경로:

- `~/.codex/skills/academic-research-suite/SKILL.md`

핵심 참조 파일:

- `skills/academic-research-suite/references/guardrails.md`
- `skills/academic-research-suite/references/modes.md`
- `skills/academic-research-suite/references/source-map.md`

## Mode mapping

이 Codex 포트는 하나의 스킬을 통해 아래 upstream 스타일 alias를 노출합니다.

| Alias | 용도 | 대표 산출물 |
| --- | --- | --- |
| `ars-plan` | 소크라테스식 논문 또는 챕터 계획 수립 | outline, section plan, open questions |
| `ars-lit-review` | literature review synthesis | related-work draft, annotated synthesis |
| `ars-outline` | full drafting 없는 구조 설계 | evidence-aware outline |
| `ars-abstract` | abstract-only drafting | abstract plus keywords |
| `ars-revision` | reviewer comment 기반 수정 | revised text plus response structure |
| `ars-revision-coach` | 수정 전 리뷰 코멘트 해석 | roadmap plus response-letter skeleton |
| `ars-citation-check` | citation integrity audit | error list, missing-support list |
| `ars-format-convert` | 형식 또는 style 변환 | conversion plan or converted artifact |
| `ars-disclosure` | AI 사용 disclosure 문구 | venue-specific disclosure text |
| `ars-full` | 단계형 end-to-end workflow | checkpointed pipeline progression |

## Usage examples

전체 프롬프트 예시는 [examples/USAGE_EXAMPLES.md](examples/USAGE_EXAMPLES.md)에 정리되어 있습니다.

빠른 예시:

```text
$academic-research-suite Help me plan a conference paper on event-based vision
Use ars-plan mode to build a paper structure for "edge AI for event cameras"
Draft a related work section in ars-lit-review style for event-based vision
Use ars-revision-coach to turn these reviewer comments into a revision roadmap
Run an ars-citation-check style audit on this section
Use ars-full to decide which pipeline stage this draft should start from
```

## 왜 Codex 포트가 단일 스킬인가

여러 slash command 대신 단일 우산 스킬을 쓰는 이유는 다음과 같습니다.

- Codex에서는 하나의 명시적 skill surface 뒤에 워크플로를 두는 쪽이 더 자연스럽습니다.
- upstream Claude 패키징은 작은 command wrapper가 많지만, Codex에서는 그 추가 계층이 꼭 필요하지 않습니다.
- 포트를 얇게 유지해야 drift가 줄고 upstream sync가 쉬워집니다.

## Update policy

- 대략 6주 단위의 upstream ARS minor release를 추적
- sync 시 `manifest.json`의 upstream commit을 갱신
- mode 이름은 upstream `commands/ars-*.md`와 정렬 유지
- Claude와 Codex 사이의 동작 차이는 README에 계속 명시

## Model portability note

upstream ARS는 Claude Code를 기준으로 조정되어 있습니다. 예를 들어 architecture나 review 깊이는 Opus, execution은 Sonnet을 전제로 합니다. 이 포트는 워크플로 의도와 mode 경계를 유지하지만, Codex에서는 다음이 달라질 수 있습니다.

- skill activation과 routing
- subagent behavior
- tool availability
- prompt length tolerance
- output tone과 checkpoint behavior

예시나 버그 리포트를 공개할 때는 이런 차이를 함께 문서화하는 것이 좋습니다.

## GitHub 공개 체크리스트

upstream contribution policy 기준 최소 sibling-distribution 체크리스트:

1. `manifest.json`에 upstream commit을 고정
2. README에 maintainer를 명시
3. sync policy를 문서화
4. model portability 차이를 문서화
5. `examples/` 아래에 최소 한 번의 end-to-end artifact set 포함

## License note

upstream ARS 프로젝트는 CC BY-NC 4.0 기반의 source-available 프로젝트입니다. 이 포트도 그 비상업적 경계를 유지하고 upstream attribution을 분명히 해야 합니다.
