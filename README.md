# 👋 Hi, I'm JONGWON LEE

**Backend Developer**  
**코드를 확인하고, 주변을 살피며 일하는 백엔드 개발자**입니다.  
계산을 짜기 전에 규칙부터 검증하고, 외부 API가 실패해도 핵심 화면은 멈추지 않는 구조를 고민합니다.

<br />

## 🚀 About Me

- **규칙부터 검증합니다.** 세금 계산 로직을 짜기 전에 간이과세자 매입세액공제가 이중으로 차감되던 오구현을 역검증으로 잡았고, 노란우산공제 로직 오류 2건을 찾아 수정했습니다.
- **숫자는 서버가, 문장은 LLM이.** LLM이 845만 원을 8,450만 원으로 옮겨 적는 오류를 겪은 뒤, 금액 계산은 서버에서 끝내고 모델에는 완성된 문자열만 넘기는 원칙을 세웠습니다.
- **외부 API는 언제든 실패한다고 가정합니다.** 부가 기능의 실패가 핵심 화면을 막지 않도록 API를 분리해서 설계합니다.
- **자동 설정 뒤를 직접 다뤄봤습니다.** Spring Boot 없이 MyBatis, HikariCP, Flyway를 직접 빈으로 구성하고 WAR를 외부 Tomcat에 배포했습니다.
- **PR 전에 내 코드를 다시 읽습니다.** 리뷰 요청 전에 직렬화 지연, 0/0 엣지케이스, 안전하지 않은 기본값 등 결함 3건을 먼저 잡았습니다.
- **옆 자리가 막히면 먼저 살핍니다.** 맡은 일이 끝나면 옆 파트부터 챙기는 게 제 방식입니다.

<br />

## 🛠 Tech Stack

### Languages
![Java](https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=openjdk&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-0175C2?style=for-the-badge&logo=dart&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

### Backend
![Spring Framework](https://img.shields.io/badge/Spring%20Framework-6DB33F?style=for-the-badge&logo=spring&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring%20Security-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white)
![MyBatis](https://img.shields.io/badge/MyBatis-C74634?style=for-the-badge&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)

### Frontend
![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=for-the-badge&logo=vuedotjs&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![Flutter](https://img.shields.io/badge/Flutter-02569B?style=for-the-badge&logo=flutter&logoColor=white)

### Database
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

### API · Integration
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=for-the-badge&logo=swagger&logoColor=black)
![OpenAI API](https://img.shields.io/badge/OpenAI%20API-412991?style=for-the-badge&logo=openai&logoColor=white)
![CODEF API](https://img.shields.io/badge/CODEF%20API-1E3A8A?style=for-the-badge&logoColor=white)
![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=for-the-badge&logo=selenium&logoColor=white)

### Tools
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Jira](https://img.shields.io/badge/Jira-0052CC?style=for-the-badge&logo=jira&logoColor=white)

<br />

## 📌 Featured Projects

### 💰 FreeFit (프리핏)
> 통장 잔고에서 나갈 세금을 미리 빼서, 프리랜서에게 **"진짜 쓸 수 있는 돈"**을 보여주는 서비스

`KB IT's Your Life 7기 종합실무 프로젝트` · `6인 팀` · `2026.07 ~ 2026.08`

- Spring Framework 5.3(non-Boot) + MyBatis 계층형 구조, WAR를 외부 Tomcat 9에 배포
- **종합소득세 계산 로직 담당**: 국세청 자료로 계산 구조(필요경비 → 기본공제 → 과세표준 → 누진세율)를 코드로 옮기고, Swagger로 입력값과 경계값을 바꿔가며 반복 검증
- **노란우산공제 오류 2건 수정**: 특정 구간 세액이 **100만 원** 과대 산정되던 문제 해결
- **AI 개요 API 분리 설계**: LLM 호출이 실패해도 리포트 숫자 화면은 그대로 뜨도록 분리, strict JSON Schema + 서버 재검증, 지난 기간 요약은 DB 캐싱
- 프롬프트를 **v1 → v5**까지 실제 호출 결과를 보며 개선
- 월간 / 연간 리포트 페이지 FE + BE 구현
- (팀 성과) 거래 동기화 **56.3초 → 29.7초**, LLM 거래 분류 정확도 **92%** (목 거래 500건 기준)

<!-- 🔗 [Repository](레포 주소) -->

---

### 👕 OOTD (Outfit Of The Day)
> 날씨와 내 옷장을 연결해 오늘 입을 옷을 골라주는 안드로이드 앱

`졸업작품 (캡스톤디자인)` · `4인 팀` · `2025.05 ~ 2025.11`

- 🏆 **2025 제8회 ICT 창의융합 캡스톤디자인 경진대회 장려상**, 학교 우수 프로젝트로 선정되어 총장 앞 발표
- **의류 데이터 수집**: Python + Selenium 무한 스크롤 크롤링, 첫 화면만 수집되던 문제를 스크롤 반복, URL 중복 제거, 로드 정체 시 종료 조건으로 해결
- **추천 기준 설계**: 옷 종류별 추천 기온 구간을 정의해, 당일 기온 하나로 후보를 바로 좁히는 1차 필터 구성
- **가상 착용 연동**: FASHN API로 추천한 옷을 사용자 전신 사진에 합성해 착용 모습을 미리 보여주는 기능 구현

<!-- 🔗 [Repository](레포 주소) -->

---

### 💘 face콕 (FaceCok)
> 축제 소개팅 부스에서 "콕"을 찔러 매칭되고, 실시간 채팅과 미션을 이어가는 행사 웹서비스

`서일대 제52회 용마대동제 실제 운영 (3일)` · `4인 팀` · `Frontend 담당`

- Next.js + TypeScript로 **가입 온보딩 7화면**과 **관리자 4화면** 구현, 온보딩 공용 컴포넌트를 먼저 만들어 단계별 화면에서 재사용
- **재로그인 흐름 개선**: 이미 가입한 사용자도 약관과 프로필을 다시 거쳐야 하던 문제를 발견해, 인증만 하면 메인으로 가는 흐름을 분리
- **관리자 화면 안전장치**: 되돌릴 수 없는 미션 완료에는 확인 단계를 한 번 더 두고, 신고 채팅은 신고 상세에서만 읽기 전용으로 열리도록 설계
- (팀 성과) 축제 3일간 실제 서비스 운영, 채팅 사용자 5명 중 4명이 "딜레이 없이 매끄러웠다"고 응답

🔗 [GitHub Organization](https://github.com/seoil-power-rangers)

<br />

## 🏆 Highlights

- 2025 ICT 창의융합 캡스톤디자인 경진대회 **장려상** (대한전자공학회 산업전자소사이어티)
- **KB IT's Your Life 7기** (멀티캠퍼스) 960시간 수료
- 대학 축제 웹서비스 **3일간 실제 운영**
- 정보처리산업기사 · SQLD · TOEIC Speaking AL

<br />

## 📊 GitHub Stats

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=jongwon-810&show_icons=true)

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=jongwon-810&layout=compact)

<br />

## 📫 Contact

[![GitHub](https://img.shields.io/badge/GitHub-jongwon--810-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/jongwon-810)
[![Portfolio](https://img.shields.io/badge/Portfolio-Notion-000000?style=for-the-badge&logo=notion&logoColor=white)](https://charm-hardcover-4c6.notion.site/1295cb8752268394aeb301d5520eec9a)
[![Email](https://img.shields.io/badge/Email-dandy0810%40naver.com-03C75A?style=for-the-badge&logo=naver&logoColor=white)](mailto:dandy0810@naver.com)
