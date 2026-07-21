<div align="center">

[English](./README.md) | **한국어** | [日本語](./README.ja.md)

# WhatNow

### Something broke. What now?

**당신의 AI는 그 버그를 고칠 수 있다. 무슨 일이 있었는지 알기만 하면.**

[웹사이트](https://whatnow.dev)

</div>

---

## Don't explain your bug. Copy the context.

AI가 버그를 못 고치는 이유는 똑똑하지 않아서가 아니다.
컨텍스트가 없어서다.

**WhatNow는 AI를 위한 Ctrl+C다.** 문제가 터지면 AI에게 필요한 모든 것 — Git diff, 스택트레이스, 로그, 터미널 히스토리, 환경 정보, Docker, Kubernetes — 을 자동으로 수집해 AI가 가장 잘 이해하는 형태로 정리한다. 복사 한 번, 붙여넣기 한 번, 해결.

### Before

```text
버그 발생
  → AI에게 설명
  → "로그를 보여주세요."
  → 로그 붙여넣기
  → "application.yml도 보여주세요."
  → 설정 붙여넣기
  → "최근 수정한 파일도 보여주세요."
  → Git diff 붙여넣기
  → 40분 소모
```

### After

```text
버그 발생
  → Copy Context
  → Paste
  → 해결
```

---

## 이렇게 동작한다

```text
WHAT HAPPENED

14:32:17  PaymentService.kt 수정
14:33:02  ./gradlew bootRun 실행
14:33:04  MongoDB 연결 실패
14:33:05  애플리케이션 시작 실패

ROOT CAUSE

최근 커밋에서 MongoDB 인증 설정이
변경되었습니다.

[ Copy for Cursor ]  [ Copy for Claude ]  [ Copy for ChatGPT ]
```

우리는 AI가 아니다. AI가 가장 좋아하는 형태로 사건을 정리하는 프로그램이다.

> **Your AI is only as good as your context.**
