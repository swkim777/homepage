---
name: "Jowon Tech Archive Design System"
version: "1.1.0"

# Color tokens (think-note 스타일의 극단적인 흑백 대비 및 하이라이트 제어)
colors:
  light:
    background: "#ffffff"       # 순수 화이트
    surface: "#f8f9fa"          # 인라인 코드 및 보조 박스
    text-main: "#111111"        # 깊은 블랙 (높은 가독성)
    text-muted: "#666666"       # 날짜, 글 번호 메타 정보
    border: "#e5e7eb"           # 미니멀한 구분선
    accent: "#0076ff"           # 링크 호버 및 주요 포인트 블루

  dark (Pure Black):
    background: "#000000"       # OLED 대응 완전한 블랙 (몰입형 지향)
    surface: "#111111"          # 인라인 코드 및 다크 보조 박스
    text-main: "#e5e7eb"        # 부드러운 화이트 (눈부심 방지)
    text-muted: "#888888"       # 다크 메타 정보
    border: "#222222"           # 어두운 구분선
    accent: "#2f95dc"           # 다크 모드 포인트 블루

# Typography tokens (Pretendard & system-ui 기반 정밀 튜닝)
typography:
  font-base: "-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif"
  font-heading: "'Pretendard', -apple-system, sans-serif"
  font-mono: "'JetBrains Mono', SFMono-Regular, Menlo, Monaco, Consolas, monospace"
  base-size: "16px"
  line-height: "1.65"           # 장문 가독성을 위해 기존 1.6에서 1.65로 미세 조정
  letter-spacing: "-0.022em"    # 자간을 좁혀 댄디하고 정갈한 인상 부여

# Layout tokens (think-note 특유의 콤팩트한 본문 폭)
layout:
  page-width: "680px"           # 시선의 좌우 이동을 최소화하여 몰입감을 높이는 상한선
  page-padding-x: "1.5rem"
  list-gap: "0.75rem"           # 리스트 아이템 간의 정밀한 간격
---

# DESIGN.md – Minimal & Focused Design System

이 문서는 think-note.com의 디자인 철학을 계승하여, 장식적 요소를 모두 걷어내고 오직 **'글의 구조와 텍스트의 힘'**에만 집중하는 시각 시스템을 규정한다.

## 1. 디자인 원칙 (Core Principles)
1. **Mono-tone Base:** 화려한 컬러 배치를 원천 배제하고, 화이트·블랙·그레이의 계층 구조로만 정보를 분류한다.
2. **Space as Element:** 선(Border)을 그어 공간을 나누기보다 여백(Padding, Margin)의 크고 작음으로 정보의 단위를 구분한다.
3. **Typography First:** 서체의 크기 차이와 두께(Font Weight) 조절이 곧 유일한 디자인 그래픽 요소이다.

## 2. 컬러 운영 규칙 (Color Usage Rules)
- **Pure Black & White:** 다크 모드 시 뒷배경은 회색조가 섞이지 않은 완전한 순수 블랙(`#000000`)을 사용하여 텍스트와의 대비를 선명하게 끌어올린다.
- **최소한의 액센트:** 링크에 마우스를 올렸을 때(`:hover`)나 꼭 기억해야 할 카테고리 태그 1개에만 제한적으로 포인트 블루(`colors.accent`)를 노출한다.

## 3. 레이아웃 & 아카이브 패턴 (Layout & Archive Patterns)

### 3.1 단일 컬럼 인덱스 (Single Column Index)
- 포스트 목록은 카드를 사용하지 않고 아래와 같은 **단순 텍스트 열(Row)** 구조로 나열한다.