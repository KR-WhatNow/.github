# 코드 & 저장소 규칙 (초안)

> 메인 리포지토리(`kr-whatnow/whatnow`) 생성 후 이 문서는 그쪽으로 이동하고, 스택 확정에 맞춰 구체화한다.

## 저장소 구조

| 저장소 | 용도 |
|---|---|
| `kr-whatnow/.github` | 조직 소개 전용 — org 프로필(한/영/일), 조직 공통 문서 |
| `kr-whatnow/whatnow` (생성 예정) | 메인 프로젝트 — **단일 레포(모노레포) + MSA** |

메인 레포 구조 예시:

```text
whatnow/
├── apps/
│   └── desktop/          # 데스크톱 앱 (Rust 또는 Go)
├── services/             # MSA 서비스 (Lambda 기반)
│   ├── context-api/
│   └── team-api/
├── infra/                # IaC (S3, CloudFront, DynamoDB)
└── docs/                 # 제안서, 로드맵, 규칙 (이 문서들이 이동할 위치)
```

## 브랜치

- `main`: 보호 브랜치. 직접 push 금지, PR로만 병합
- `feature/<이름>`: 기능 개발
- `fix/<이름>`: 버그 수정

## 커밋 메시지

[Conventional Commits](https://www.conventionalcommits.org/) 형식을 따른다.

```text
feat: 컨텍스트 수집기에 Docker 로그 추가
fix: 시크릿 마스킹이 멀티라인 토큰을 놓치는 문제 수정
docs: 로드맵 Phase 1 업데이트
chore: CI 워크플로 추가
refactor: 수집기 인터페이스 분리
test: Git diff 수집기 테스트 추가
```

## 코드 규칙

- 언어별 린터/포매터 규칙은 Desktop 스택(Rust vs Go) 확정 후 구체화한다
  - Rust 선택 시: `rustfmt` + `clippy` 기본 설정
  - Go 선택 시: `gofmt` + `golangci-lint` 기본 설정
- **시크릿(API 키, 토큰, 비밀번호)은 절대 커밋하지 않는다** — 우리가 시크릿 마스킹을 파는 팀이다
- 모든 PR은 리뷰 1인 이상 승인 후 병합

## 문서

- 조직 프로필: 영어 기본, 한국어/일본어 번역본 유지 (`profile/README*.md`)
- 제품 카피·슬로건은 영어 원문을 유지한다
