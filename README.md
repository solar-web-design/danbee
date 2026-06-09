# 단비파워 DANBEE POWER — 브랜드 랜딩 페이지

> 지속 가능한 에너지로 미래의 가치를 만든다 · *Powering Sustainable Value*

신재생에너지(태양광·풍력·연료전지) 발전사업 기업 **단비파워**의 브랜드 랜딩 페이지 프로토타입입니다.

---

## 프로젝트 개요

| 항목 | 내용 |
|------|------|
| **회사** | 단비파워 (DANBEE POWER) |
| **사업** | 신재생에너지 발전사업 — 태양광 / 풍력 / 연료전지 |
| **포지셔닝** | 깨끗한 에너지 인프라를 제공하는 **에너지 플랫폼 기업** |
| **슬로건** | Powering Sustainable Value (지속가능한 가치에 에너지를 더하다) |
| **상태** | 디자인 방향 확정 · 랜딩 프로토타입 (2026-06-09) |
| **유형** | 단일 페이지, self-contained HTML (빌드 도구 없음) |

---

## 디자인 방향 — "Cinematic Editorial"

3가지 방향을 탐색한 뒤 **B (Cinematic Editorial)** 를 채택했습니다.
(탐색 산출물은 [`_design-exploration/`](_design-exploration/) 참고)

| 안 | 컨셉 | 결과 |
|----|------|------|
| A | Operations Intelligence (데이터 대시보드형) | 신뢰감↑, 다소 기술 편향 |
| **B** | **Cinematic Editorial (사진·매거진형)** | ✅ **채택** — 감성·환경가치 전달 최상 |
| C | Swiss Brutalist (초대형 타이포) | 임팩트↑, 보수적 발주처엔 과감 |

### 디자인 시스템
- **팔레트**: 페이퍼 `#F4F1EA` / 포레스트 잉크 `#1C2B22` / 세이지 `#7A8D84` / 선라이즈 액센트 `#E08A3C`
- **타이포그래피**
  - 영문 디스플레이: **Bodoni Moda** (고대비 세리프, 이탤릭 강조)
  - 한글 디스플레이: **Noto Serif KR** (Bodoni에 한글 글리프 없음 → 페어링)
  - 본문: Plus Jakarta Sans (영문) / Pretendard (한글)
- **레이아웃**: 풀블리드 시네마틱 사진 + 넉넉한 여백 + 좌우 교차 밴드 + 스크롤 reveal

### 페이지 구조
1. **히어로** — 새벽 풍력 발전기 풀블리드 + 대형 한글 세리프 헤드라인 (수직 중앙)
2. **인트로** — 오버사이즈 풀쿼트 + 회사 소개
3. **사업영역 3밴드** — 01 태양광 / 02 풍력 / 03 연료전지 (좌우 교차, 다크밴드 포함)
4. **숫자 섹션** — 100% · 24/7 · 0g · 3분야 (태양광 사진 다크 오버레이)
5. **사업추진 프로세스** — 사업개발 → 인허가 → EPC 시공 → 운영·자산관리 (넘버드 리스트)
6. **클로징 CTA** — 노을 한국 풍경 + 문의 버튼
7. **푸터**

---

## 기술 스택 / 구조

- **순수 HTML/CSS/JS** — 프레임워크·빌드 없음. `index.html` 단일 파일에 CSS·JS 인라인
- 폰트: Google Fonts (Bodoni Moda, Noto Serif KR, Plus Jakarta Sans) + Pretendard CDN
- 인터랙션: IntersectionObserver 스크롤 reveal, 히어로 통과 후 네브 라이트→솔리드 전환
- 반응형: 데스크탑 / 태블릿 / 모바일 (860px·520px 브레이크포인트)

```
danbee/
├── index.html              # 랜딩 페이지 (self-contained)
├── img/                    # 로컬 호스팅 이미지 (4장)
│   ├── wind.jpg            # 히어로 · 풍력
│   ├── solar.jpg           # 태양광 · 숫자 섹션 배경
│   ├── fuelcell.jpg        # 연료전지
│   └── landscape.jpg       # 클로징 (노을 풍경)
├── docs/
│   └── 개발계획서.md        # 상세 디자인 결정 · 로드맵 · TODO
├── _design-exploration/    # 탐색 3안 미리보기 (아카이브)
│   ├── A-operations.png
│   ├── B-editorial.png
│   └── C-brutalist.png
└── README.md
```

---

## 로컬 실행

빌드 불필요. 정적 서버로 열면 됩니다 (폰트·이미지 로드를 위해 `file://` 말고 HTTP 권장).

```bash
cd danbee
python -m http.server 8080
# → http://localhost:8080/index.html
```

---

## ⚠️ 확정 전 교체 필요 항목

| 항목 | 현재 | 조치 |
|------|------|------|
| **사진 4장** | AI 생성 이미지 | 실제 단비파워 발전소 **실사**로 교체 권장 (신뢰도↑) |
| 연료전지 사진 | 우하단 "THE FUTURE IS CLEAR" 텍스트 박힘 | 깨끗한 이미지로 교체 |
| 이메일 | `contact@danbeepower.co.kr` (가정) | **실제 연락처** 확정 |
| 도메인/회사정보 | placeholder | 사업자정보·주소·전화 확정 |
| 로고 | 인라인 SVG 3-블레이드 (브랜드 가이드 재현) | 공식 로고 파일 확보 시 교체 |
| 통계 수치 | 100%/24/7/0g/3분야 (개념값) | 실제 발전용량(MW)·실적으로 보강 |

---

## 개발 이력

| 날짜 | 내용 |
|------|------|
| 2026-06-09 | 브랜드 가이드 수신 → Stitch MCP로 3방향 탐색 → **B(Editorial) 확정** → self-contained 코드 변환, 로컬 이미지 호스팅, 사업추진 프로세스 섹션 구성, 히어로 수직 중앙 정렬 |

> 디자인 탐색·워크플로우 상세는 `E:\Coding\stitch-web\danbee-power-landing/` 참고
