# RheaPhoenix 웹사이트 — 작업 안내 (Claude용)

MR Solution(엠알솔루션)의 의료기기 **Rhea**, **Phoenix**를 의료업계에 홍보·판매하기 위한 웹사이트입니다.
이 파일은 어느 PC, 어느 Claude 환경(Claude Code 터미널 / claude.ai/code)에서 열어도 같은 방식으로 작업을 이어가기 위한 안내입니다.

## 작업 원칙 (반드시 지킬 것)

- **요청하지 않은 항목은 만들지 않는다.** 필요해 보이는 것이 있으면 먼저 사용자에게 묻고 상의한 뒤 만든다.
- 사용자는 한국어로 소통한다. 답변도 한국어로 한다.

## 처음 디자인 요청 (사용자 원문 요약)

당신은 경험 많은 웹 개발자이자 UI/UX 전문가입니다. 사용자 친화적이고 디자인 전문 분야입니다. 다음 요구사항에 맞는 웹사이트를 만들어주세요.

- 주요 기능: Rhea, Phoenix 제품 홍보 및 판매
- 타겟 사용자: 의료업계
- 원하는 스타일/분위기: https://u2clab.com/ 페이지에서 상단 header와 hero 영역만 똑같이
- Nav 메뉴: About Us / Rhea / Phoenix / Contact Us
- Hero 이미지: 사용자가 준 파일(hero-01.jpg, Rhea_s.png, Pheonix_s.png) 사용
- 로고: mrlogo3.svg

## 이후 사용자 결정 사항

- Nav 서브메뉴 삭제 (메뉴 4개만)
- 요청하지 않은 항목은 만들지 말고 상의하며 제작
- GitHub Pages로 웹 링크 공개, 여러 PC에서 이어서 작업

## 여러 PC 동기화 규칙

- 작업을 시작하면 가장 먼저 `git pull` 로 다른 PC에서 올린 최신본을 받는다.
- 작업이 끝나면 커밋하고 `main`에 푸시한다. (사용자가 따로 말하지 않으면 브랜치/PR 대신 main에 바로 반영)
- 푸시 후 1~2분 뒤 GitHub Pages에 반영된다.
- 이 파일의 "진행 현황"은 작업이 끝날 때마다 갱신해서 함께 커밋한다.

## 주소

- 웹사이트 (GitHub Pages): https://mrs36.github.io/RheaPhoenix/
- 저장소: https://github.com/mrs36/RheaPhoenix (Public, 배포 브랜치 `main`, 루트)

## 파일 구조

- `index.html` — 사이트 전체. CSS·JS·로고(SVG)가 한 파일 안에 들어 있다. 히어로 제품 이미지는 `img/web/` 파일을 링크한다.
- `img/` — 사용자가 올린 원본 이미지 (PNG, 투명 배경). 파일명 규칙: `hero-{rhea|phoenix|rhea-phoenix}-{pc|mo}.png`
- `img/web/` — 원본을 투명 여백 잘라내고 webp로 변환한 사이트용 이미지. 원본을 바꾸면 다시 변환해서 교체한다.
  - PC/모바일은 `<picture>`로 1023px 이하에서 `-mo` 이미지 사용
- `.claude/skills/figma-export/SKILL.md` — 디자인 화면을 Figma 파일로 내보내는 규칙(스킬). Figma로 보낼 때는 이 스킬을 따른다.

## 현재 구성

- 참고 디자인: https://u2clab.com/ 의 상단 header + hero 영역
- 콘텐츠 너비 (좌우 여백 최소 64px, 가운데 정렬)
  - 헤더(로고·Nav·아이콘): 최대 1792px (1920 화면 기준 좌우 64px)
  - 히어로 텍스트·제품 이미지: 최대 1440px (1920 화면 기준 좌우 240px). 히어로 배경은 전체 너비
  - 슬라이드 인디케이터: 헤더 콘텐츠(1792px) 왼쪽 바깥 여백에 위치. 모바일(1023px 이하)은 기존 배치(좌우 20~24px) 유지
- Header: 흰 배경, 높이 100px 고정. 로고(왼쪽) / Nav 가운데 / 검색·공유 아이콘(오른쪽)
  - Nav: About Us / Rhea / Phoenix / Contact Us (서브메뉴 없음 — 사용자 요청으로 삭제)
  - 모바일(1023px 이하): 햄버거 메뉴
- Hero: 전체 화면형 — 헤더 + 히어로 = 화면 높이 100vh (첫 화면에 히어로만 보임, 모바일 포함)
- Hero 슬라이더: 2장 페이드 슬라이더(5초 자동재생, 왼쪽 세로 인디케이터 + 일시정지)
  1. Rhea — "Rhea / 폐쇄형 백 농축 시스템"
  2. Phoenix — "Phoenix / 시린지 농축 시스템"
  - Rhea+Phoenix 함께 있는 슬라이드는 사용자 요청으로 삭제 (원본 `img/hero-rhea-phoenix-*.png`는 남겨둠)
- Features 섹션 (참고: u2clab.com 의 Service 섹션 레이아웃, "Service" → "Features", 파랑 rgb(0,99,242))
  1. Rhea (`#rhea`): 텍스트 왼쪽 / 이미지 오른쪽(화면 오른쪽 끝까지). 특징 3개 — 폐쇄형 시스템, 특허 레이섬 볼 구조, 스마트 센서 정밀 수집. 이미지: Rhea 일회용 키트(`img/feature-rhea-kit.jpg`)
  2. Phoenix (`#phoenix`): 이미지 왼쪽 / 텍스트 오른쪽. 특징 4개 — 안전성·효율성·정밀함·편의성 (Phoenix 카탈로그 문구). 이미지: PRP·PPP 주사기 사진(`img/feature-phoenix-prp.png`, Phoenix 영문 브로셔에서 추출, 해상도 낮음)
  3. 파란 영역(`.band`, rgb(0,99,242)): 참고 사이트의 Experiences 자리. 내용 없이 색만 — 추후 상의
  - 특징 항목: 참고 사이트와 같게 제목 + 회색 ↗ 화살표 + 회색 설명 (작은 파란 라벨 없음). 화살표는 현재 장식용(링크 없음 — 상세 페이지 생기면 연결)
- 제품 자료 (사용자 제공, 저장소에는 없음): Rhea 카탈로그, Phoenix 카탈로그(국문), Phoenix 브로셔(영문), 대만 허가증·특허증·GMP 인증서 이미지, 유튜브 영상 https://www.youtube.com/watch?v=AJ8wMS4t8UA
  - 인증서 유효기간 지남(허가증 2024-11, 특허 2024-10, GMP 2021-10) → 사이트 게재 전 갱신본 확인 필요
- 색: 제목 #0e1024, 설명 파랑 #2448c9, 브랜드 네이비 #171b46, 레드 #ec2227
- 폰트: Pretendard(설치된 경우) → Noto Sans KR(Google Fonts)

## 진행 현황

- 완료: header + hero 영역, GitHub Pages 배포
- 완료: 히어로 전체 화면형(100vh) 적용
- 완료: 콘텐츠 너비 레이아웃 적용 — 헤더 1792px, 히어로 1440px
- 완료: 히어로 제품 이미지 교체 (사용자 제공 img/ → img/web/ webp, PC 3장 + 모바일 3장)
- 완료: 히어로에서 Rhea+Phoenix 슬라이드 삭제 → 제품별 2장만
- 완료: Features 섹션(Rhea / Phoenix) + 파란 영역(색만)
- 완료: Figma 내보내기 스킬(`figma-export`) 저장 — 링크의 Figma 파일로, 컴포넌트 적용 상태로, 컴포넌트 원본은 별도 페이지에
- 완료: `img/` 폴더 이미지(히어로 PC/모바일, 로고, 캡쳐화면) 저장소에 업로드 — PSD는 제외, index.html에는 아직 미적용
- 미결 (사용자와 상의 필요):
  - 임의로 넣었던 요소의 유지 여부: '자세히 보기' 버튼, SCROLL 표시, 검색·공유 아이콘
  - 히어로 문구는 임시 문구 — 실제 제품 사양/문구 확인 후 교체
  - 파란 영역 내용, About Us / Contact Us 섹션은 아직 없음 — 구성은 사용자와 상의 후 제작
  - 참고 사이트 동적 인터랙션 추가 요청 — 이 클라우드 환경에서 u2clab.com 접속 차단되어 확인 불가. 사용자와 방식 상의 중
  - Phoenix 특징 이미지 해상도 낮음(482px) — 고해상도 사진 있으면 교체
