# Codex용 Ko Style Writing

[English README](README.md)

이 스킬은 Codex에서 설득력 있는 academic writing revision을 수행하기 위한 패키지입니다. 읽기 쉬운 영어 연구 문장, 보수적인 claim 처리, citation-aware revision에 초점을 둡니다.

## 하는 일

- 단순 요약이 아니라 argument flow 중심으로 academic prose를 다듬음
- 문장 명확성과 explicit antecedent를 개선함
- claim이 적절한 근거와 범위를 갖는지 점검함
- live LaTeX 편집에서도 비교적 안전하게 동작함

## 하지 않는 일

- citation, result, dataset, novelty claim을 꾸며내지 않음
- 근거보다 강한 claim을 정당화하지 않음
- advisor review를 대체하지 않음

## 설치 방법

### 방법 1: 스킬 복사

```bash
mkdir -p ~/.codex/skills
cp -R skills/ko-style-writing ~/.codex/skills/
```

### 방법 2: 개발용 심볼릭 링크

```bash
mkdir -p ~/.codex/skills
ln -s "$(pwd)/skills/ko-style-writing" ~/.codex/skills/ko-style-writing
```

## 주요 파일

- `skills/ko-style-writing/SKILL.md`
- `skills/ko-style-writing/references/professor-preferences.md`
- `skills/ko-style-writing/references/model-paper-patterns.md`
- `skills/ko-style-writing/references/revision-passes.md`

## 예시 프롬프트

```text
$ko-style-writing Revise this introduction so it reads like a persuasive argument
$ko-style-writing Check this chapter for claim strength and citation gaps
$ko-style-writing Apply a flow pass and sentence pass to this LaTeX section
$ko-style-writing Rewrite this contribution paragraph without AI-like wording
```

## Revision passes

- `advisor pass`: 설득력과 committee defensibility 점검
- `flow pass`: 문단과 섹션 논리 보수
- `sentence pass`: 가독성과 명시성 개선
- `citation pass`: 근거와 citation 지원 점검
- `defense pass`: 심사 상황에서 claim 범위 조정
- `latex-safe pass`: LaTeX 민감 구조 보존

## 학위논문 저장소에서의 동작

학위논문 저장소 안에서 사용할 때는 아래 로컬 표기와 citation 관례를 유지합니다.

- `$E_{\text{thr}}$` 와 `$T_{\text{exp}}$`
- SISA의 `Spatially-Indexed Sparsity-Aware`
- `~\cite{key}` 형태의 LaTeX citation key

## 공개용 메모

이 공개용 README는 의도적으로 교수님 실명 브랜딩을 포함하지 않습니다. 저장소 랜딩 페이지에서 advisor identity를 노출하지 않도록 기능 중심으로 설명합니다.
