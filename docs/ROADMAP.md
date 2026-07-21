# WhatNow 로드맵

> 앞으로 해야 할 일. 메인 리포지토리(`kr-whatnow/whatnow`) 생성 후 이 문서는 그쪽으로 이동한다.

## Phase 0 — 검증 & 준비

- [x] 아이디어 정리 및 제안서 작성 ([PROPOSAL.md](./PROPOSAL.md))
- [x] 서비스명 확정: **WhatNow**
- [ ] 도메인 확보: whatnow.dev
- [ ] 메인 리포지토리 생성: `kr-whatnow/whatnow` (단일 레포 + MSA)
- [ ] Desktop 기술 스택 확정: Rust vs Go
- [ ] 컨텍스트 수집 PoC: Git Diff + StackTrace + 로그를 하나의 패키지로 묶는 최소 프로토타입

## Phase 1 — MVP (데스크톱 앱)

- [ ] 데스크톱 앱 뼈대 (트레이 상주 + 단축키)
- [ ] 수집기(Collector) 구현
  - [ ] Git Diff / 최근 수정 파일 / 현재 브랜치
  - [ ] StackTrace
  - [ ] Recent Logs (애플리케이션 로그)
  - [ ] Terminal History
  - [ ] Environment (OS, IDE, 런타임, Memory, CPU)
  - [ ] Docker Logs
  - [ ] Kubernetes Events
- [ ] **시크릿 마스킹**: API 키·비밀번호·토큰 자동 감지 및 마스킹 (MVP 필수)
- [ ] AI Context Package 생성기
- [ ] Likely Root Cause 추정
- [ ] AI별 프롬프트 템플릿: Copy for Cursor / Claude / ChatGPT / Gemini
- [ ] 무료 티어 제한 (하루 5회)
- [ ] 랜딩 페이지 (whatnow.dev)

## Phase 2 — 연동

- [ ] GitHub Issue 자동 생성
- [ ] Jira Ticket 자동 생성
- [ ] PR Description 자동 생성
- [ ] Slack 자동 전송
- [ ] 유료 플랜 결제

## Phase 3 — 팀 기능

- [ ] 팀 공유: 동일 버그 자동 공유
- [ ] Team Dashboard
- [ ] Team Analytics
