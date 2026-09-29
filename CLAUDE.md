# RheaPhoenix 웹사이트 — 작업 안내 (Claude용)

MR Solution(엠알솔루션)의 의료기기 **Rhea**, **Phoenix**를 의료업계에 홍보·판매하기 위한 웹사이트입니다.
이 파일은 어느 PC, 어느 Claude 환경(Claude Code 터미널 / claude.ai/code)에서 열어도 같은 방식으로 작업을 이어가기 위한 안내입니다.

## 작업 원칙 (반드시 지킬 것)

- **요청하지 않은 항목은 만들지 않는다.** 필요해 보이는 것이 있으면 먼저 사용자에게 묻고 상의한 뒤 만든다.
- 사용자는 한국어로 소통한다. 답변도 한국어로 한다.
- **사이트 문구는 제공 자료(카탈로그·사용자 제공 문구)를 있는 그대로 쓴다.** 조합·요약·변형·새로 지어내기가 필요하면 반드시 먼저 사용자에게 안(案)을 보여주고 허락받은 뒤 반영한다.

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
- Hero 슬라이더: 2장 페이드 슬라이더(3.5초 자동재생 — 사용자 요청으로 5초에서 단축, 왼쪽 세로 인디케이터 + 일시정지)
  1. Rhea — "Rhea / 자가 혈액 생리활성 분자 증강 시스템" (사용자가 직접 수정). 설명: 최신 혈액 원심분리 기술을 적용한 완전 자동화 시스템으로 / 고품질 BaM 생산. 자가 유래 BaM을 효과적으로 농축
  2. Phoenix — "Phoenix / 시린지 농축 시스템"
  - PC(1024px 이상)에서 제목은 한 줄 유지(nowrap), 제품 이미지는 텍스트 아래 레이어 — 겹쳐도 됨(사용자 결정). 모바일은 기존처럼 줄바꿈
  - 하단 흐르는 문구: "Autologous BaM(Bio-active Molecules) Enrich System" — 150pt(=200px, 모바일 60px, 처음 300pt에서 사용자 요청으로 1/2), 히어로 세로 가운데 배치(사용자 요청, 이전엔 하단 -40px), 흰색 30% 투명(사용자 요청으로 50%→30%), 굵게. 오른쪽→왼쪽으로 계속 흐름(60초 한 바퀴, 문구 2개 이어 붙인 marquee). 참고: miracell.co.kr #mainAbout. 레이어: 배경 위·제품 이미지와 제목 아래. 두 슬라이드에 각각 넣음
  - Rhea+Phoenix 함께 있는 슬라이드는 사용자 요청으로 삭제 (원본 `img/hero-rhea-phoenix-*.png`는 남겨둠)
- Features 섹션 (참고: u2clab.com 의 Service 섹션 레이아웃, "Service" → "Features", 파랑 rgb(0,99,242))
  1. Rhea (`#rhea`): 텍스트 왼쪽 / 이미지 오른쪽(화면 오른쪽 끝까지). 설명: "자가 혈액 생리활성 분자 증강 시스템 / Autologous Bio-active Molecules Enrich System"(사용자 선택 B안, 원문). 특징 3개 — 카탈로그 Core Competency 원문(영문 제목 / 한글 설명): Functional Close system / 폐쇄형 시스템으로 오염 원천 차단, Patented Latham Bowl Design / 특허된 레이섬 볼 구조로 세포 품질 유지, Precision collection / 스마트 센서로 5분 내 정밀 수집 — 폐쇄형 시스템, 특허 레이섬 볼 구조, 스마트 센서 정밀 수집. 이미지: Rhea 일회용 키트(`img/feature-rhea-kit.jpg`)
  2. Phoenix (`#phoenix`): 이미지 왼쪽 / 텍스트 오른쪽. 설명: 카탈로그 원문 문장(Phoenix는 원클릭 자동화 시스템으로 …). 특징 4개 — 안전성·효율성·정밀함·편의성 (국문 카탈로그 원문과 대조해 "인한", "압도적" 누락 보완 완료). 이미지: PRP·PPP 주사기 사진(`img/feature-phoenix-prp.png`, Phoenix 영문 브로셔에서 추출, 해상도 낮음)
  3. 파란 영역(`.band`, rgb(0,99,242)): 참고 사이트의 Experiences 자리. 내용 없이 색만 — 추후 상의
  - 특징 항목: 참고 사이트와 같게 제목 + 회색 ↗ 화살표 + 회색 설명 (작은 파란 라벨 없음). 화살표는 현재 장식용(링크 없음 — 상세 페이지 생기면 연결)
  - 인터랙션 (u2clab.com Service 섹션 코드 확인 후 동일 적용)
    - 스크롤 등장: fadeInUp(아래 100px→제자리, 1초, 이미지 1.8초), 한 번만. 지연: Features 0 / 제목 .3s / 설명 .5s / 항목 .4s~ / 이미지 0
    - 특징 항목 hover(1024px 이상): ↗ 화살표 검정 + 오른쪽 위 3px 이동(.5s)
    - 'View More' 원형 마우스 포인터는 사용자 요청으로 삭제
    - 미적용: 항목 hover 시 이미지 전환(제품별 이미지 1장뿐), 모바일 이미지 스와이프 슬라이드(레이아웃 변경) — 필요 시 상의
- 제품 자료 (사용자 제공, 저장소에는 없음): Rhea 카탈로그, Phoenix 카탈로그(국문), Phoenix 브로셔(영문), 대만 허가증·특허증·GMP 인증서 이미지, 유튜브 영상 https://www.youtube.com/watch?v=AJ8wMS4t8UA
  - 인증서 유효기간 지남(허가증 2024-11, 특허 2024-10, GMP 2021-10) → 사이트 게재 전 갱신본 확인 필요
  - 파일 목록: Rhea_catalog_ver1.pdf, Rhea_DM-Ophthalmology_eng.pdf, Phoenix_catalog.pdf(국문), PhoenixDM2_EN.pdf(영문 브로셔), Q_A.pptx
- 색: 제목 #0e1024, 설명 파랑 #2448c9, 브랜드 네이비 #171b46, 레드 #ec2227
- 폰트: Pretendard(설치된 경우) → Noto Sans KR(Google Fonts)

## 제품 핵심 문구 (사용자 제공 — 사이트 문구는 여기 기준으로 작성)

- 두 제품 공통 문구: **Autologous Bio-active Molecules Enrich System**
- 강조 단어: **레이섬 볼 시스템**, **BaM(생체활성분자 / 생리활성분자)**

### Rhea — 자가 혈액 생리활성 분자 증강 시스템
- 영문: Rhea Autologous Bio-active Molecules Enrich System
- Core Competency of Rhea
  - Functional Close system — 폐쇄형 시스템으로 오염 원천 차단
  - Patented Latham Bowl Design — 특허된 레이섬 볼 구조로 세포 품질 유지 (특허번호 Nr. 202016000191)
  - Precision collection — 스마트 센서로 5분 내 정밀 수집
- 5 minutes / Total Process!!
- 카탈로그 설명: 최신 혈액 원심분리 기술을 적용한 완전 자동화 시스템, 소프트웨어와 광학 센서로 제어. 80mL 전혈에서 5분 내 약 10~18mL의 고품질 BaM 생산. 자가 유래 BaM을 효과적으로 농축
- The Best Supporting Therapy: 미용·피부 재생 / 상처 치료·재생 / 안과 치료 / 정형외과 치료
- 사양: Model ABM2, 원심 1000~6000RPM±2%, 수집 10~18ml, All-in-one button, 전혈 최소 80ml, 6kg, W28×D25×H23cm, BaM 형태 Gel·Eye Drops·Injections·Spray

### Phoenix — Phoenix Autologous BaM(Bio-active Molecules) Enrich System
- 다양한 성장인자를 결합한 복합 치료 솔루션
- Phoenix는 원클릭 자동화 시스템으로 사용이 간편하며, 유연한 공정을 갖춘 정밀 BaM(생리활성분자) 제조 시스템으로, 고품질 혈소판(DEPA 기준 충족)을 효율적으로 생성합니다.
- Phoenix의 고농축 PRP 기술 강조
- 국문 카탈로그 원문 (사용자가 이미지로 제공, 그대로 옮김)
  - 1. 제품특징
    - 안전성 — 완전 밀폐형 시스템 / 공기 노출 및 감염 위험을 원천 차단한 추출 방식
    - 효율성 — 6분 내 신속한 처리 / 레이섬 볼을 이용한 고속 회전으로 인한 신속한 처리
    - 정밀함 — 2.5배 높은 혈소판 농도 / 광학 센서 기술로 구현한 기준치 대비 2.5배 압도적 농축률
    - 편의성 — 자동화 고농축 시스템 / 원클릭으로 고농축 PRP와 PPP를 자동으로 동시 추출
  - 표지 체크 항목: 안전성 / 효율성 / 경제성 / 사용 편의성
  - DEPA 분류에 기초한 피닉스성능: 혈소판 용량 높음 / 공정 효율성 좋음 / BaM의 순도 높음
  - * DEPA는 혈소판 치료(PRP)의 품질을 평가하는 국제 기준으로써 Dose(혈소판 총량), Efficiency(채취 효율), Purity(순도), Activation(활성화 여부)로 분류됩니다.
  - 2. Phoenix 작동 원리: 체혈 ▸ 프로토콜 선택 ▸ 장착 ▸ 혈액 주입 ▸ 원심분리 시작 ▸ PRP.PPP 수집
    - 01 환자에게서 60ml / 80ml의 전혈을 채취하여 항응고제가 든 혈액백이나 주사기에 담습니다.
    - 02 화면에서 원하는 방식(Protocol)을 선택합니다.
    - 03 화면에 보이는 지침에 따라 일회용 키트, 주사기, 혈액백을 기기에 장착합니다.
    - 04 시작 버튼을 누르면 혈액 펌프가 작동하여 혈액백/주사기에 있는 피를 원심분리 용기(bowl)로 보냅니다
    - 05 시스템이 원심분리 과정을 시작합니다. 레이섬 볼 시스템 *특허번호 : 3204349
    - 06 회전이 끝나면 펌프가 작동하여 PPP와 PRP를 각각 두 개의 주사기에 나누어 담습니다.
  - Phoenix의 고농축 PRP 기술: 피닉스는 일반적인 수동 방식과 달리 혈소판 밀도가 가장 높은 버피 코트(Buffy Coat) 층을 정밀 추출하여, 고농축을 상징하는 붉은 빛(Reddish color)의 고농축 PRP를 완성합니다. (혈장 45% / 적혈구 55% / 혈소판·백혈구 1% — 카탈로그 표기 그대로)

## 진행 현황

- 완료: header + hero 영역, GitHub Pages 배포
- 완료: 히어로 전체 화면형(100vh) 적용
- 완료: 콘텐츠 너비 레이아웃 적용 — 헤더 1792px, 히어로 1440px
- 완료: 히어로 제품 이미지 교체 (사용자 제공 img/ → img/web/ webp, PC 3장 + 모바일 3장)
- 완료: 히어로에서 Rhea+Phoenix 슬라이드 삭제 → 제품별 2장만
- 완료: Features 섹션(Rhea / Phoenix) + 파란 영역(색만)
- 완료: Features 섹션 인터랙션(스크롤 등장, 화살표 hover) — 참고 사이트 코드 기준. View More 포인터는 삭제
- 완료: Rhea 히어로 이미지 교체 (사용자가 새로 올린 img/hero-rhea-{pc,mo}.png → img/web/ webp, PC 1352×1407 / 모바일 730×788). 원본 캔버스가 같아도 그림 영역 높이가 달라지면 자동 여백 자르기로 확대되므로, 이전 이미지와 같은 배율(같은 자르기 높이)로 맞춤)
- 완료: 히어로 하단 흐르는 문구(marquee) 추가
- 완료: Features 문구 원문으로 교체 — Rhea 설명(B안)·특징 3개, Phoenix 설명·특징 4개(국문 카탈로그 대조)
- 완료: 제품 핵심 문구(사용자 제공 + Rhea 카탈로그) CLAUDE.md에 저장 — 자료 파일 원본 보관 위치는 사용자와 상의 중(저장소가 Public)
- 완료: Figma 내보내기 스킬(`figma-export`) 저장 — 링크의 Figma 파일로, 컴포넌트 적용 상태로, 컴포넌트 원본은 별도 페이지에
- 완료: `img/` 폴더 이미지(히어로 PC/모바일, 로고, 캡쳐화면) 저장소에 업로드 — PSD는 제외, index.html에는 아직 미적용
- 미결 (사용자와 상의 필요):
  - 임의로 넣었던 요소의 유지 여부: '자세히 보기' 버튼, SCROLL 표시, 검색·공유 아이콘
  - 히어로 문구는 임시 문구 — 핵심 문구 기준 교체를 한 번 적용했으나 "폰트가 이상하다"는 사용자 요청으로 되돌림(한글 부제 축소·굵은 강조가 원인으로 추정). 다시 적용 시 기존 폰트 스타일 유지하고 상의
  - 사용자 확인 없이 조합·작성된 기존 문구 점검 필요: 히어로 제목·설명 전체(임시), Features의 Rhea·Phoenix 설명 문장(f-desc) 등 — 원문 그대로인지 사용자와 대조 후 교체
  - 파란 영역 내용, About Us / Contact Us 섹션은 아직 없음 — 구성은 사용자와 상의 후 제작
  - Phoenix 특징 이미지 해상도 낮음(482px) — 고해상도 사진 있으면 교체
