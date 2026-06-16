---
name: "Personal Tech Blog"
version: "1.0.0"

# Color tokens
colors:
  background: "#0f172a"       # 전체 배경 (예: 다크 네이비)
  surface: "#020617"          # 카드/포스트 배경
  primary: "#38bdf8"          # 링크, 주요 버튼
  primary-soft: "#0ea5e9"
  accent: "#a855f7"           # 코드/태그 하이라이트
  text-main: "#e5e7eb"        # 본문 텍스트
  text-muted: "#9ca3af"       # 메타 정보
  border-subtle: "#1e293b"

# Typography tokens
typography:
  font-base: "system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif"
  font-heading: "'Pretendard', system-ui, sans-serif"
  font-mono: "'JetBrains Mono', ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, 'Liberation Mono', 'Courier New', monospace"
  base-size: "16px"
  line-height: "1.6"

# Layout tokens
layout:
  page-width: "720px"         # 본문 최대 폭
  page-padding-x: "1.5rem"
  section-gap: "3rem"
  card-radius: "0.75rem"
  card-padding: "1.5rem"

# Components (요약 정의)
components:
  header:
    height: "64px"
    sticky: true
  post-card:
    show-date: true
    show-tags: true
    show-reading-time: true
  code-block:
    theme: "dark"
    show-line-numbers: true
---

# DESIGN.md – Personal Tech Blog

이 문서는 개인 기술 블로그의 시각적 언어와 UI 원칙을 정의한다.  
목표는 **읽기 좋은** 다크 테마, 집중 가능한 본문 레이아웃, 그리고 코드 친화적인 스타일이다.

## 1. 브랜드 / 톤

- 키워드: minimal, focused, calm, pragmatic
- 주요 독자: 개발자, 디자이너, AI/생산성에 관심 있는 기술 직군
- 톤:
  - 과장된 그래픽보다 타이포와 간격 위주
  - 장식적인 요소보다 정보 전달 우선
  - 명확한 대비, 여유 있는 여백

## 2. 레이아웃

- 전체 레이아웃:
  - 가운데 정렬된 single-column 레이아웃
  - 최대 폭은 `layout.page-width`를 따른다.
- 페이지 구조:
  - 상단 고정 헤더: 블로그 로고(텍스트) + 최소한의 네비게이션 (Home, Blog, About)
  - 본문 컨테이너는 상하 여백을 넉넉히 두고, 모바일에서도 좌우 패딩 유지
- 반응형:
  - 모바일에서는 헤더 메뉴를 아이콘 또는 한 줄 텍스트로 단순화
  - 이미지, 코드블록, 표는 모두 가로 스크롤이나 줄바꿈으로 깨지지 않도록 처리

## 3. 색상

- 배경:
  - 전체 배경은 `colors.background`를 사용한다.
  - 카드나 포스트 박스는 `colors.surface`를 사용해 살짝 떠 보이게 한다.
- 텍스트:
  - 본문 텍스트는 항상 `colors.text-main`
  - 날짜, 태그, 부가 설명은 `colors.text-muted`
- 링크:
  - 기본 링크 색은 `colors.primary`
  - hover 시 `colors.primary-soft`로 조금 더 밝아지며 underline 추가
- 강조:
  - 코드 키워드, 태그 pill 등에 `colors.accent` 사용
- 규칙:
  - 배경 위에 순수 흰색(#ffffff) 사용은 최소화하고, 텍스트 컬러 토큰만 사용한다.
  - 대비가 충분히 나도록 WCAG AA 이상 수준을 유지한다.

## 4. 타이포그래피

- 기본:
  - 본문 폰트: `typography.font-base`
  - 기본 크기: `typography.base-size`
  - 줄 높이: `typography.line-height`
- 제목:
  - h1: 블로그 제목이나 포스트 제목에 사용, 약 2.2rem, 굵기 700
  - h2: 글 내부 주요 섹션 제목, 약 1.6rem, 굵기 600
  - h3: 세부 섹션, 약 1.3rem, 굵기 600
  - 제목은 `typography.font-heading`을 사용
- 코드:
  - 인라인 코드: `typography.font-mono` 사용, 살짝 작은 크기, 배경에 약한 하이라이트
  - 블록 코드: `typography.font-mono`, 다크 테마 코드 하이라이트 적용

## 5. 구성 요소

### 5.1 헤더

- 좌측: 블로그 이름(텍스트 로고, h1/h2 크기)
- 우측: 간단한 네비게이션 링크 2~4개
- 가로 구분선이나 그림자는 아주 얕게 사용하거나 생략
- 스크롤 시 살짝 배경 불투명도 증가 정도만 적용

### 5.2 포스트 목록 카드

- 구조:
  - 제목 (h2 스타일)
  - 메타: 날짜, 카테고리/태그, 예상 읽기 시간
  - 짧은 요약(2~3문장)
- 스타일:
  - 카드 배경: `colors.surface`
  - 모서리: `layout.card-radius`
  - 패딩: `layout.card-padding`
  - hover 시 약한 scale 및 그림자 (아주 미묘하게)

### 5.3 포스트 상세

- 본문 최대 폭: `layout.page-width`
- 목차(선택):
  - h2 기준 자동 생성
  - 좌측 또는 상단에 간단한 목록 형태
- 이미지:
  - 가급적 전체 폭보다 약간 작은 사이즈, 캡션 옵션
  - 스크린샷에는 얇은 border와 약한 radius 적용

## 6. 블로그 콘텐츠 패턴

- 포스트 시작:
  - 제목 아래에 메타 정보를 한 줄에 모아 보여준다.
  - 예: `2026-06-12 · Frontend · 8 min read`
- 본문:
  - 한 단락은 3~5문장 정도로 유지
  - 코드블록, 리스트, 이미지 등을 섞어 가독성을 유지
- 강조:
  - 중요한 정의/결론은 인용구(quote) 또는 callout 스타일로 표시
  - 너무 많은 색상 강조는 피하고, 구조와 타이포로 의미를 구분

## 7. SEO 및 접근성 (요약)

- 제목 태그 계층 구조를 올바르게 유지 (h1은 페이지당 하나)
- 링크 텍스트는 “여기 클릭” 대신 의미 있는 문장 사용
- 대비, 폰트 크기, 키보드 포커스 스타일을 유지해 접근성을 확보

## 8. 향후 확장 아이디어

- 다국어 지원: 한국어/영어 토글 시에도 동일한 레이아웃과 스타일 유지
- 다크/라이트 테마 토글: 토큰 레벨에서 색상 세트만 바꿔 적용
- 태그 기반 아카이브 페이지: 태그 칩 스타일을 재사용
