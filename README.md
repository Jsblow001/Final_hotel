# 🏨 Ciel Hotel (호텔 통합 예약 및 관리 시스템)
> **파이널 프로젝트 (팀 프로젝트)**
> 
> 호텔 'Le Ciel'의 브랜드 가치를 높이는 **사용자 메인 UI**와 지점 운영 최적화를 위한 **통합 관리자 시스템**을 구축했습니다. 특히 **프로모션 혜택이 예약 결제에 실시간으로 적용되는 자동 할인 로직**과 데이터 기반의 수익 통계 시스템을 전담하여 개발했습니다.

<br>

## 1. 📅 프로젝트 기간
- 2026.02 - 2026.04 (약 2개월)

<br>

## 2. 🛠 기술 스택

### 💻 Backend
<img src="https://img.shields.io/badge/Java%2017-007396?style=for-the-badge&logo=java&logoColor=white"/> <img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white"/> <img src="https://img.shields.io/badge/Mybatis-black?style=for-the-badge&logo=apache&logoColor=white"/> <img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white"/>

### 🗄️ Database
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white"/>

### 🌐 Frontend
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/> <img src="https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white"/> <img src="https://img.shields.io/badge/Bootstrap%204-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white"/> <img src="https://img.shields.io/badge/Chart.js-FF6384?style=for-the-badge&logo=chartdotjs&logoColor=white"/>

### 🔧 Tools
<img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white"/> <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/>

<br>

## 👤 3. 담당 역할 및 기여도 (My Role)
- **메인 및 고객 접점 서비스 (User Interface)**
  - **메인 레이아웃:** 호텔 브랜드 아이덴티티를 반영한 메인 페이지 디자인 및 동적 콘텐츠 배치
  - **고객 소통 채널:** 공지사항(Notice), QnA, FAQ 게시판의 백엔드/프론트엔드 통합 개발
- **프로모션 및 예약 시스템 연동 (Business Logic)**
  - **실시간 할인 연동:** 특정 프로모션 기간 내 예약 시, DB 할인율을 대조하여 **결제 금액이 자동 계산되는 로직** 구현
  - **콘텐츠 매니지먼트:** 프로모션 이벤트 등록 및 활성화 상태에 따른 자동 노출 시스템 구축
- **운영 관리 시스템 (Admin System)**
  - **수익 관리 대시보드:** 누적 예약 데이터를 집계하여 지점별/기간별 매출을 `Chart.js`로 시각화
  - **통합 배너 관리:** 관리자가 직접 제어 가능한 이미지 업로드 및 노출 우선순위 설정 기능

<br>

## 🏗 4. DB 설계 (ERD)
- **설계 포인트:** 프로모션(Promotion)과 예약(Reservation) 간의 연동을 위해 외래키 관계를 설정하고, 다양한 게시판과 배너를 효율적으로 관리하기 위해 **콘텐츠 테이블을 모듈화**하여 설계했습니다.

<div align="center">
  <img src="https://via.placeholder.com/800x400.png?text=Le+Ciel+Hotel+Project+ERD" width="800" alt="Le Ciel ERD"/>
</div>

<br>

## 🚀 5. 핵심 기능 및 트러블슈팅

### ✅ 프로모션-예약 시스템 연동 및 동적 할인 로직
- **문제 상황:** 프로모션이 단순 안내용 게시글로만 존재할 경우, 실제 예약 시 혜택 적용이 누락되거나 관리자가 수동으로 처리해야 하는 운영상 번거로움 발생.
- **해결 방안:** 예약 API 호출 시 활성화된 프로모션 정보를 검증하고, **할인율을 적용한 최종 결제 금액을 산출하는 Service 계층 로직**을 구현함.
- **결과:** 사용자 경험(UX)을 개선하고 예약 전환율을 높였으며, 할인된 데이터가 수익 통계에 정확히 반영되도록 정합성 확보.

### ✅ 다차원 수익 통계 산출 및 데이터 시각화
- **문제 상황:** 분산된 대량의 결제 데이터를 실시간 대시보드에 출력할 때 발생하는 성능 이슈와 복잡한 쿼리 연산 필요.
- **해결 방안:** PostgreSQL의 집계 함수(`SUM`, `COUNT`)와 복합 JOIN을 활용해 DB 레벨에서 1차 가공 후, 가용 데이터를 `Chart.js`로 시각화함.
- **결과:** 관리자가 한눈에 매출 흐름을 파악하고 지점 운영 상태를 즉각 분석할 수 있는 환경 제공.

<br>

## 📺 6. 실행 화면
| 메인 페이지 UI | 관리자 수익 대시보드 | 프로모션 및 배너 관리 |
| :---: | :---: | :---: |
| <img src="이미지주소" width="300"/> | <img src="이미지주소" width="300"/> | <img src="이미지주소" width="300"/> |
| 브랜드 아이덴티티 메인 구성 | Chart.js 기반 매출 분석 | 할인 연동 프로모션 제어 |

<br>

## 📂 7. 프로젝트 구조 (My Part 중심)
```text
src/main/java/js
  ├── admin (운영 관리)
  │    ├── controller/AdminController.java  # 수익 통계 및 배너 관리 API
  │    ├── service/AdminService.java        # 매출 집계 및 시각화 데이터 가공 로직
  │    └── model (dao, vo)                  # PostgreSQL 연동 및 통계 객체
  ├── board (고객 소통 및 콘텐츠)
  │    ├── controller/BoardController.java  # 공지/QnA/FAQ 게시판 제어
  │    ├── service/BoardService.java        # 게시글 관리 및 유효성 검사
  │    └── model (dao, vo)                  # 콘텐츠 데이터 매핑
  └── promotion (할인 연동)
       ├── controller/PromotionController.java # 프로모션 로직 제어
       └── service/PromotionService.java      # 예약 시스템 연동 및 할인율 산출

src/main/webapp/WEB-INF/views/js
  ├── main.jsp                              # 메인 서비스 화면
  ├── admin/ (수익 대시보드, 배너 관리)
  └── board/ (공지사항, 프로모션 목록, QnA)
