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

- `index.html` — 사이트 전체. CSS·JS·로고(SVG)·이미지(webp data URI)가 모두 한 파일 안에 들어 있다.
  - 이미지 base64 문자열이 매우 길므로, 수정할 때는 해당 부분을 건드리지 말고 텍스트/CSS/HTML 구조만 찾아서 고친다.

## 현재 구성

- 참고 디자인: https://u2clab.com/ 의 상단 header + hero 영역
- Header: 흰 배경, 높이 100px 고정. 로고(왼쪽) / Nav 가운데 / 검색·공유 아이콘(오른쪽)
  - Nav: About Us / Rhea / Phoenix / Contact Us (서브메뉴 없음 — 사용자 요청으로 삭제)
  - 모바일(1023px 이하): 햄버거 메뉴
- Hero: 3장 페이드 슬라이더(5초 자동재생, 왼쪽 세로 인디케이터 + 일시정지)
  1. Rhea+Phoenix 함께 있는 이미지 — "정밀한 농축, 신뢰할 수 있는 결과"
  2. Rhea — "Rhea / 폐쇄형 백 농축 시스템"
  3. Phoenix — "Phoenix / 시린지 농축 시스템"
- 색: 제목 #0e1024, 설명 파랑 #2448c9, 브랜드 네이비 #171b46, 레드 #ec2227
- 폰트: Pretendard(설치된 경우) → Noto Sans KR(Google Fonts)

## 진행 현황

- 완료: header + hero 영역, GitHub Pages 배포
- 미결 (사용자와 상의 필요):
  - 임의로 넣었던 요소의 유지 여부: '자세히 보기' 버튼, SCROLL 표시, 검색·공유 아이콘
  - 히어로 문구는 임시 문구 — 실제 제품 사양/문구 확인 후 교체
  - Hero 아래 섹션(About Us, Rhea, Phoenix, Contact Us)은 아직 없음 — 구성은 사용자와 상의 후 제작
