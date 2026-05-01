# 🏨 Ciel Hotel (호텔 통합 예약 및 관리 시스템)
> **파이널 프로젝트 (팀 프로젝트)**
> 
> 호텔 'Le Ciel'의 브랜드 가치를 결정하는 **사용자 메인 UI**와 운영 효율을 위한 **통합 관리자 시스템**을 구축했습니다. **Docker와 Jenkins를 활용한 CI/CD 환경**에서 **Oracle DB**를 연동하여, 프로모션 혜택이 예약 결제에 실시간 적용되는 로직과 수익 관리 대시보드를 전담 개발했습니다.

<br>

## 1. 📅 프로젝트 기간
- 2026.02 - 2026.03 (약 3주)

<br>

## 2. 🛠 기술 스택

### 💻 Backend
<img src="https://img.shields.io/badge/Java%2017-007396?style=for-the-badge&logo=java&logoColor=white"/> <img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white"/> <img src="https://img.shields.io/badge/Mybatis-black?style=for-the-badge&logo=apache&logoColor=white"/> <img src="https://img.shields.io/badge/Spring%20Security-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white"/>

### 🗄️ Database
<img src="https://img.shields.io/badge/Oracle-F80000?style=for-the-badge&logo=oracle&logoColor=white"/>

### 🚀 DevOps & Deployment
<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"/> <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white"/> <img src="https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white"/>

### 🌐 Frontend
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/> <img src="https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white"/> <img src="https://img.shields.io/badge/Thymeleaf-005F0F?style=for-the-badge&logo=thymeleaf&logoColor=white"/> <img src="https://img.shields.io/badge/Bootstrap%204-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white"/> <img src="https://img.shields.io/badge/Chart.js-FF6384?style=for-the-badge&logo=chartdotjs&logoColor=white"/>

<br>

## 👤 3. 담당 역할 및 기여도 (My Role)
- **메인 및 고객 서비스 시스템 (Full-stack)**
  - **메인 레이아웃:** **Thymeleaf**를 활용하여 브랜드 아이덴티티를 반영한 동적 메인 페이지 구현
  - **고객 소통 게시판:** 공지사항(Notice), QnA, FAQ 시스템의 DB 설계 및 전체 로직 담당
- **프로모션 및 예약 연동 (Business Logic)**
  - **동적 할인 시스템:** 프로모션과 예약 시스템을 연동하여, **예약 시 실시간으로 할인율을 계산하고 결제 금액에 반영**하는 백엔드 로직 구현
- **운영 관리 시스템 (Admin System)**
  - **수익 관리 대시보드:** 실시간 결제 데이터를 집계하여 지점별/기간별 수익 현황을 `Chart.js`로 시각화
  - **콘텐츠 배너 관리:** 메인 배너 및 프로모션 영역의 이미지 업로드 및 노출 스케줄링 관리 시스템 구축
- **CI/CD 인프라:** Docker 컨테이너 기반 개발 환경 구축 및 Jenkins를 활용한 AWS 배포 자동화 참여

<br>

## 🏗 4. DB 설계 (ERD)
- **설계 포인트:** 프로모션(Promotion)과 예약(Reservation) 간의 연동을 위해 Oracle의 관계형 모델을 설계하고, 효율적인 콘텐츠 관리를 위해 게시판 테이블을 모듈화했습니다.

<div align="center">
  <img src="https://via.placeholder.com/800x400.png?text=Le+Ciel+Hotel+Project+ERD" width="800" alt="Le Ciel ERD"/>
</div>

<br>

## 🚀 5. 핵심 기능 및 트러블슈팅

### ✅ 프로모션-예약 시스템 연동 및 동적 할인 로직
- **문제 상황:** 프로모션이 안내용 게시글로만 존재하여 실제 결제 시 혜택 적용이 자동화되지 않는 문제 발생.
- **해결 방안:** 예약 API 호출 시 활성화된 프로모션 정보를 검증하고, **할인율을 적용한 최종 결제 금액을 산출하는 Service 계층 로직**을 구현함.
- **결과:** 사용자 경험(UX)을 개선하고 예약 전환율을 높였으며, 수익 통계 데이터의 정확도 확보.

### ✅ 다차원 수익 통계 산출 및 데이터 시각화
- **문제 상황:** 분산된 대량의 결제 데이터를 실시간 대시보드에 출력할 때 발생하는 성능 이슈와 복잡한 쿼리 연산 필요.
- **해결 방안:** Oracle의 집계 함수(`SUM`, `COUNT`)와 복합 JOIN을 활용해 DB 레벨에서 1차 가공 후, 가용 데이터를 `Chart.js`로 시각화함.
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
/* Backend: com.spring.app */
├── admin      # 수익 통계 대시보드 및 배너 관리 모듈
├── board      # 공지사항, FAQ, QnA 콘텐츠 관리 모듈
└── promotion  # 할인율 계산 및 예약 시스템 연동 로직

/* Resources: Mybatis & Thymeleaf Templates */
src/main/resources
  ├── mapper
  │    ├── admin.xml           # 매출 및 방문자 통계 집계 쿼리
  │    ├── board.xml           # 공지사항 및 QnA 데이터 처리 쿼리
  │    └── promotion.xml       # 프로모션 할인 및 예약 연동 쿼리
  └── templates                # Thymeleaf HTML 템플릿
       ├── main.html           # 메인 서비스 화면
       ├── admin/              # 수익 통계 및 관리 UI
       └── board/              # 공지사항, 프로모션 리스트, QnA 화면
