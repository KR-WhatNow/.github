# WhatNow — 프로젝트 제안서

> **Something broke. What now?**
>
> **Don't explain your bug. Copy the context.**

| 항목 | 내용 |
|---|---|
| 프로젝트명 | **WhatNow** (초기 가칭: ContextKit / Debug Context) |
| 도메인 | whatnow.dev |
| 형태 | **데스크톱 앱** (확정) |
| 한 줄 소개 | AI가 버그를 못 고치는 이유는 똑똑하지 않아서가 아니라, 컨텍스트가 없어서다. 우리는 AI가 문제를 가장 잘 이해할 수 있는 형태로 프로젝트의 모든 컨텍스트를 자동 수집하고 정리한다. |
| 작성일 | 2026-07 |
| 상태 | 제안 |

---

## 1. 배경 — 시장이 바뀌었다

예전에는 이랬다.

```text
개발자 → Google → StackOverflow
```

지금은 이렇다.

```text
개발자 → Cursor / Claude / ChatGPT
```

문제는 AI가 아니다. **AI에게 상황을 설명하는 과정**이다.

Cursor, Claude Code, Gemini CLI, Codex CLI, Windsurf — AI 코딩 도구 사용자는 폭발적으로 늘고 있다. 그런데 AI에게 컨텍스트를 전달하는 툴은 거의 없다. 이 간극이 우리의 기회다.

---

## 2. 문제 정의 (Pain Point)

현재의 바이브 코딩은 이런 식이다.

```text
버그 발생
  ↓
StackTrace 복사
  ↓
Cursor
  ↓
"정보가 부족합니다."
  ↓
로그 붙여넣기
  ↓
"application.yml도 보여주세요."
  ↓
Git Diff 붙여넣기
  ↓
"최근 수정한 파일도 보여주세요."
  ↓
Docker 로그
  ↓
K8s 로그
  ↓
30분 ~ 2시간
```

결국 AI는 문제를 못 푸는 게 아니다.
**개발자가 AI에게 사건을 설명하는 데 시간을 다 쓴다.**

사람들이 실제로 느끼는 짜증은 버그 자체가 아니라, AI에게 같은 설명을 계속하는 것이다. 그래서 이 제품의 핵심 메시지는 디버깅이 아니라 **컨텍스트**다.

---

## 3. 해결책

```text
버그 발생
  ↓
WhatNow
  ↓
자동 수집
  ↓
AI Context Package 생성
  ↓
Copy
  ↓
Cursor / Claude / ChatGPT
  ↓
5분 안에 해결
```

### AI Context Package 예시

```text
====================================
PROJECT
  Spring Boot 3.5.15
  Java 21
  MongoDB
  Kubernetes
====================================
CURRENT BRANCH
  feature/payment
====================================
RECENT GIT DIFF
  ...
====================================
RECENTLY MODIFIED FILES
  PaymentService.kt
  PaymentRepository.kt
  MongoConfig.kt
====================================
TERMINAL COMMANDS
  kubectl apply
  helm upgrade
  docker compose up
====================================
STACKTRACE
  ...
====================================
APPLICATION LOGS
  ...
====================================
DOCKER LOGS
  ...
====================================
KUBERNETES EVENTS
  ...
====================================
ENVIRONMENT
  Java / Spring / OS / Memory / CPU
====================================
LIKELY ROOT CAUSE
  ...
====================================
PROMPT FOR AI
  You are a senior backend engineer...
====================================

[ Copy for Cursor ]
```

끝.

---

## 4. 포지셔닝 & 차별점

### 우리는 AI가 아니다

우리는 **AI가 가장 좋아하는 형태로 사건을 정리하는 프로그램**이다.

- AI를 대체하지 않는다. AI가 가장 잘 일할 수 있는 **입력**을 만들어 준다.
- "버그 해결을 빠르게"가 아니라 **"AI를 위한 Ctrl+C"**로 포지셔닝한다.

이 문장은 개발자라면 거의 즉시 이해한다.

- "맞아. AI한테 맨날 설명하고 있네."
- "로그만 붙여넣으면 또 이것저것 더 달라고 하지."
- "차라리 필요한 걸 한 번에 주면 되잖아."

### Before / After

```text
Before                          After

버그 발생                        버그 발생
  ↓                               ↓
AI에게 설명                      Copy Context
  ↓                               ↓
추가 질문                        Paste
  ↓                               ↓
또 설명                          해결
  ↓
또 복붙
  ↓
40분
```

---

## 5. 제품 경험

에러가 발생하면 개발자는 이렇게 생각한다.

```text
"What now...?"
```

그리고 서비스가 답한다.

```text
WhatNow:
  Here's what happened.
  Copy this to your AI.
```

### 랜딩 페이지

> **WhatNow**
>
> Something broke. What now?
>
> Your AI can fix it. It just needs to know what happened.
>
> `[ Get Context ]`

### 결과 화면

```text
WHAT HAPPENED

14:32:17
You modified PaymentService.kt

14:33:02
Ran ./gradlew bootRun

14:33:04
MongoDB connection failed

14:33:05
Application startup failed

ROOT CAUSE

MongoDB authentication configuration
was changed in the latest commit.

[ Copy for Cursor ]
[ Copy for Claude ]
[ Copy for ChatGPT ]
```

---

## 6. MVP 범위

**형태: 데스크톱 앱 (확정)**

### 자동 수집

- Git Diff
- StackTrace
- Recent Logs
- Terminal History
- Environment (OS, IDE)
- Docker
- Kubernetes

### 버튼 하나

```text
[ Generate Context ]  또는  [ Copy Context ]
```

### AI 선택

```text
Cursor / Claude / ChatGPT / Gemini
```

버튼을 누르면 각 AI에 맞는 프롬프트를 생성한다.

---

## 7. 로드맵 (요약)

| 단계 | 기능 |
|---|---|
| MVP 이후 | GitHub Issue 자동 생성 |
| | Jira Ticket 자동 생성 |
| | PR Description 자동 생성 |
| | Slack 자동 전송 |
| | 팀 공유 — 동일 버그 자동 공유 |

상세 일정과 체크리스트는 [ROADMAP.md](./ROADMAP.md) 참고.

---

## 8. 기술 스택

| 영역 | 스택 |
|---|---|
| Desktop | Rust 또는 Go (확정 예정) |
| Backend | Lambda, S3, CloudFront, DynamoDB |
| AI | Claude, OpenAI, Gemini, 로컬 LLM |

---

## 9. 수익 모델

| 플랜 | 내용 |
|---|---|
| 무료 | 하루 5회 |
| 유료 | 무제한, GitHub 연동, Jira 연동, Team Dashboard, Team Analytics |

---

## 10. 시장

Cursor, Claude Code, Gemini CLI, Codex CLI, Windsurf — AI 코딩 도구 사용자가 폭발적으로 늘고 있다.

그런데 **AI에게 컨텍스트를 전달하는 툴은 거의 없다.**

---

## 11. 네이밍 & 슬로건

### 이름: WhatNow

`WhatHappened`는 과거를 설명하는 서비스다. 무슨 일이 있었는지 알려준다.

반면 `WhatNow`는 **문제가 발생한 순간의 개발자 감정을 정확히 찌른다.**

```text
에러 발생

개발자:
"What now...?"
```

짧고, 기억하기 쉽고, 제품 경험과 자연스럽게 연결된다. 도메인(whatnow.dev)을 그대로 브랜드로 쓴다.

### 슬로건

**최종:**

> **Don't explain your bug. Copy the context.**

**후보:**

1. AI doesn't need smarter answers. It needs better context.
2. Stop explaining. Start fixing.
3. The fastest way to fix a bug is giving AI the whole story.
4. Don't copy logs. Copy context.
5. Your AI is only as good as your context.

---

## 12. 리스크 & 열린 질문

### 경쟁 리스크: AI 도구의 컨텍스트 수집 내장화

Cursor, Claude Code 등은 이미 파일 읽기·명령 실행으로 자체 컨텍스트 수집을 점점 내장하고 있다. 우리의 방어선은 다음 두 가지다.

- **IDE 밖의 런타임 컨텍스트**: 터미널 히스토리, Docker/K8s 로그와 이벤트, 실행 환경 — IDE 내장 AI가 접근하기 어려운 영역
- **툴 독립성**: 특정 AI에 종속되지 않고 Cursor/Claude/ChatGPT/Gemini 어디로든 가져갈 수 있는 패키지

### 보안 / 프라이버시

로그·환경변수·터미널 히스토리에는 API 키, 비밀번호, 토큰이 섞여 들어온다. **시크릿 자동 감지·마스킹은 MVP 필수 기능**이다. 이것이 빠지면 신뢰를 잃는 사고가 한 번에 터진다.

### 배포 전략

데스크톱 앱은 확정. 다만 보완 채널로 다음을 언제 추가할지는 열린 질문이다.

- CLI (터미널 중심 개발자용)
- MCP 서버 (Claude Code 등이 WhatNow의 컨텍스트를 직접 끌어가는 통로 — 경쟁자가 아니라 유통 채널이 될 수 있다)

### 기타 열린 질문

- 무료 하루 5회 제한이 습관 형성에 충분한가
- 컨텍스트 수집·정리를 어디까지 로컬에서 처리하고, 어디부터 클라우드(LLM 요약 등)에 의존할 것인가
- Likely Root Cause 추정의 정확도 기준 — 틀린 추정은 없는 것보다 나쁠 수 있다

---

*이 문서는 메인 리포지토리(`kr-whatnow/whatnow`) 생성 후 그쪽으로 이동한다.*
