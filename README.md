# MyCode 프로젝트 개요

<img width="49%" alt="image" src="https://github.com/user-attachments/assets/4308e330-d32e-4031-9db7-23ddfe374b56" /> <img width="49%" alt="image" src="https://github.com/user-attachments/assets/caf1d91c-362c-495b-9d76-e028a03b39e5" />
<img width="49%" alt="image" src="https://github.com/user-attachments/assets/4308e330-d32e-4031-9db7-23ddfe374b56" /> <img width="49%" alt="image" src="https://github.com/user-attachments/assets/caf1d91c-362c-495b-9d76-e028a03b39e5" />

**MyCode**는 사용자 취향 기반 공연·전시·축제 추천 서비스입니다.<br>
사용자의 성향 테스트 결과를 바탕으로 전시, 공연, 축제, 행사 등 다양한 문화 콘텐츠를 맞춤 추천합니다.<br>
공공 Tour API 연동을 통해 검증된 문화 데이터를 제공하며, 소셜 로그인 기반의 간편한 사용자 경험을 지원합니다.<br>
iOS 및 Android를 모두 지원하는 모바일 앱으로, 2025.10 ~ 2026.02까지 운영되었습니다. 

---

## 기술 스택
> **개발 기간:** 2025.08 ~ 2026.02  
> **담당 역할:** Backend 개발 및 Infrastructure 구축  
> **팀 구성:** 총 7명 (기획 1명, 디자인 2명, 프론트엔드 2명, 백엔드 및 인프라 2명)

| 분류 | 기술 (Stack) |
| :--- | :--- |
| **Backend** | ![Java](https://img.shields.io/badge/Java_17-ED8B00?style=flat-square&logo=openjdk&logoColor=white) ![Spring Boot](https://img.shields.io/badge/Spring_Boot_3.5-6DB33F?style=flat-square&logo=springboot&logoColor=white) ![JPA](https://img.shields.io/badge/Spring_Data_JPA-6DB33F?style=flat-square) ![QueryDSL](https://img.shields.io/badge/QueryDSL_5.0-0099CC?style=flat-square) <br> ![Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white) ![OAuth2](https://img.shields.io/badge/OAuth2-000000?style=flat-square) ![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)  |
| **DB & Cache** | ![MySQL](https://img.shields.io/badge/MySQL_8.0-4479A1?style=flat-square&logo=mysql&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) |
| **Infrastructure** | ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white) ![AWS EC2](https://img.shields.io/badge/AWS_EC2-FF9900?style=flat-square&logo=amazonec2&logoColor=white) ![AWS RDS](https://img.shields.io/badge/AWS_RDS-527FFF?style=flat-square&logo=amazonrds&logoColor=white) ![AWS S3](https://img.shields.io/badge/AWS_S3-569A31?style=flat-square&logo=amazons3&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Github Actions](https://img.shields.io/badge/Github_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white) |
| **Build** | ![Gradle](https://img.shields.io/badge/Gradle-02303A?style=flat-square&logo=gradle&logoColor=white) |
| **Documentation** | ![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=flat-square&logo=swagger&logoColor=black) |
| **Communication** | ![Notion](https://img.shields.io/badge/Notion-000000?style=flat-square&logo=notion&logoColor=white) ![Slack](https://img.shields.io/badge/Slack-4A154B?style=flat-square&logo=slack&logoColor=white) ![Figma](https://img.shields.io/badge/Figma-F24E1E?style=flat-square&logo=figma&logoColor=white) |

---

## 아키텍처

<img width="1268" height="768" alt="image" src="https://github.com/user-attachments/assets/a92e8d26-b8ce-4b99-bdf6-4c391f51e464" />

---

## 주요 기능

### 회원 및 인증
- **소셜 로그인**: Kakao, Apple OAuth2를 이용한 간편 로그인 지원
- **JWT 인증**: Access Token / Refresh Token 기반 인증 및 갱신
- **역할 기반 접근 제어**: 일반 사용자(NORMAL)와 관리자(ADMIN) 역할 구분

### 성향 테스트 & 맞춤 추천
- **성향 테스트**: 설문 기반 성향 분석 (외향/내향, 활동적/조용한, 감각적/이성적 등 5가지 차원)
- **맞춤 추천**: 사용자 성향 점수와 콘텐츠 성향 연관도를 기반으로 개인화된 문화 행사 추천
- **지역 기반 추천**: 사용자 선호 지역을 반영한 콘텐츠 필터링

### 콘텐츠 탐색
- **카테고리별 탐색**: 전시(EXHIBITION), 공연(PERFORMANCE), 축제(FESTIVAL), 행사(EVENT) 분류
- **인기 콘텐츠**: 조회수 기반 인기 행사 노출
- **주간 추천**: 이번 주 진행 중인 문화 행사 제공
- **키워드 검색**: 콘텐츠명 및 태그 기반 검색 (최근 검색어, 인기 검색어 지원)

### 찜 & 일정 관리
- **찜 기능**: 관심 있는 문화 행사 저장 및 목록 조회
- **일정 등록**: 참여 예정 행사를 캘린더에 등록하여 월별/일별 조회

### 콘텐츠 수집
- **공공 Tour API 연동**: 한국관광공사 Tour API를 통한 공식 문화 행사 데이터 자동 수집
- **이미지 저장**: AWS S3 연동을 통한 콘텐츠 이미지 관리

---

## 설계 원칙 및 기술적 고려사항

- **QueryDSL 기반 동적 쿼리**: 카테고리, 지역, 날짜 범위 등 복합 필터링 조건을 타입 안전하게 처리
- **JWT 무상태 인증**: Redis 기반 토큰 관리로 서버 확장성 확보
- **표준화된 API 응답**: `BaseResponse` 래퍼를 통한 일관된 응답 형식 유지
- **공공 데이터 연동**: Spring Cloud OpenFeign을 활용한 외부 API 통신 추상화
