# ai-vault

내가 자주 쓰는 AI 작업 방식, 프롬프트, 체크리스트, 참고 저장소를 모아두는 개인용 저장소다.

이 저장소의 목적은 단순히 프롬프트를 쌓는 것이 아니라, 반복해서 쓰는 작업 방식을 재사용 가능한 형태로 정리하는 것이다. 법률 질문 설계, 대학 과제 작성, 디스플레이 실험 보고서, PDF 문서 처리, GitHub/Codex 작업 규칙을 중심으로 관리한다.

## 기본 사용법

ChatGPT나 Codex에게 이 저장소를 참고하라고 한 뒤, 필요한 작업 영역을 지정한다.

예시:

```text
ai-vault의 legal-question-designer 스킬을 참고해서 이 사건 질문을 정리해줘.
```

```text
ai-vault의 display-report-writer 규칙에 맞춰 실험 고찰을 다듬어줘.
```

```text
starred-repos.md에 있는 후보 중 지금 작업에 쓸 만한 레포를 골라줘.
```

## 구조

```text
AGENTS.md
skills/
  legal-question-designer.md
  display-report-writer.md
  github-repo-reader.md
  pdf-document-helper.md
checklists/
  legal-brief-checklist.md
  report-style-checklist.md
  source-verification-checklist.md
templates/
  prompt-template.md
  skill-template.md
examples/
  legal-question-example.md
  report-paragraph-example.md
starred-repos.md
```

## 운영 원칙

확인되지 않은 사실은 단정하지 않는다.

사용자의 감정이나 주장과 실제 확인 가능한 사실을 구분한다.

좋아 보이는 답변보다 실제로 다시 쓸 수 있는 결과물을 우선한다.

AI에게 단순 검색을 맡기기보다, 질문을 구조화하고 반론을 만들고 초안을 개선하는 파트너로 사용한다.
