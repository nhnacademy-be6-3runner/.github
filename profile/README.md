# 3조업고튀어(3runner)
배포 사이트 들어가기 : 📚[3runner.shop](https://3runner.shop/)
(8/30일 부로 MySQL, Redis, RabbitMQ, Elasticsearch 지원이 끊겨 웹사이트가 닫혔습니다)

[![Watch the video](https://img.youtube.com/vi/pJXM93sb6Ic/maxresdefault.jpg)](https://www.youtube.com/watch?v=pJXM93sb6Ic)

서버별 소스 리포지토리 경로
- front 서버 [front](https://github.com/nhnacademy-be6-3runner/3runner-front)
- backend-api 서버 [bookstore](https://github.com/nhnacademy-be6-3runner/3runner-bookstore)
- copuon-api 서버 [coupon](https://github.com/nhnacademy-be6-3runner/3runner-coupon)
- auth 서버 [auth](https://github.com/nhnacademy-be6-3runner/3runner-auth)
- batch 서버 [batch](https://github.com/nhnacademy-be6-3runner/3runner-batch)
- gateway 서버 [gateway](https://github.com/nhnacademy-be6-3runner/3runner-gateway)
- eureka 서버 [eureka](https://github.com/nhnacademy-be6-3runner/3runner-eureka)


## 1. 팀원
- 김병우 [helloJosh](https://github.com/helloJosh)
- 김은비 [ubiies](https://github.com/ubiies)
- 오연수 [okeio](https://github.com/okeio)
- 유지아 [lyujia](https://github.com/lyujia)
- 정주혁 [jjh260811](https://github.com/jjh260811)
- 한민기 [dkssudrhd](https://github.com/dkssudrhd)

## 2. ERD
![bookstore (6)](https://github.com/user-attachments/assets/348f72ed-2481-4b00-8643-8b6c970c36dd)
- 꾸준히 변경할 때 마다 버전 관리하여 0.04버전이 최종 버전이 되었습니다.

### DB관리자
- 정주혁
- [DDL코드보기](https://github.com/nhnacademy-be6-3runner/3runner-docs/blob/main/db0.04.sql)


## 3. 아키텍처
![systemarchitecture drawio](https://github.com/user-attachments/assets/0ed2866d-a631-4871-9b0f-55b7342d3c71)

#### 네트워크 설계
- Spring Gateway가 각 서버를 효율적으로 찾아가기 위해 Spring Eureka를 사용하여 서버의 내부 정보를 캐싱하여 네트워크를 설계하였습니다.
- Client Side 로드밸런싱을 하기위해 OpenFeign을 사용하여 각 서버에 효율적으로 접근하도록 네트워크를 설계하였습니다

#### 인증
- 여러 서버에서 같은 토큰으로 인증을 관리하기 위해서 JWT 토큰을 도입하였습니다.

## 4. CI/CD
![cicd (1)](https://github.com/user-attachments/assets/4dd7b06a-aeb3-455d-8cf4-34de8f26e6b8)
- 코드가 머지했을 때만 깃 액션이 반응하게 파이프라인을 설계했습니다.
- 프론트, 북스토어 서버는 배포 빈도가 높기 떄문에 스크립트를 작성하여 도커 stats를 활용해 무중단 배포를 구현하였습니다.

## 5. 프로젝트 관리
체계적이고 효율적인 관리를 위해, [Github Project](https://github.com/orgs/nhnacademy-be6-3runner/projects/1)을 활용하여 프로젝트를 진행하였습니다.

### BackLog, RoadMap 활용
![image](https://github.com/user-attachments/assets/ea9ffcef-046d-4db0-9947-bc38295b8bef)
- 매일 9:30에 RoadMap과 BackLog를 활용하여 스크럼 회의를 진행했습니다.

### Scrum
![image](https://github.com/user-attachments/assets/d5105eff-b9a1-4782-84cc-ad51d8b37d6b)
- 스크럼은 평일, 하루에 한 번씩 진행하였습니다.

### Issue관리
<img width="1448" alt="image" src="https://github.com/user-attachments/assets/6c28a5d3-8826-4c53-9aef-9c8c4dd6d244">
- 개발시 Issue가 나왔을때 Issue관리를 통해서 해결하였습니다.

### Manage
![image](https://github.com/user-attachments/assets/1b7e4369-bc0c-4112-a27e-d4e48064732c)
- git flow branch 전략은 main/develop/feature로 나누어 개발을 하였습니다.
- feature는 각각 기능을 만들때 사용하였고
- develop은 기능이 완료되고 확인이 되었을때 pr을 올려 merge를 진행했습니다.
- main은 배포시에 merge를 진행하였습니다.

### PR, CodeReview
![Screenshot 2024-07-16 at 7 52 31 PM](https://github.com/user-attachments/assets/5b3495b6-871d-47e2-875b-191d68a6ef6e)
- 완성되지 않은 코드도 PR로 올려 팀원들이 코드리뷰를 지속적으로 진행하였고
- 팀원들이 전부 한번씩 확인해야만 코드를 merge할 수 있게 하였습니다.

### 일정관리 - WBS
![Screenshot 2024-07-16 at 7 54 54 PM](https://github.com/user-attachments/assets/800e96e8-8be1-44ff-9cc6-c7eae51a2af6)
- 일정은 도서, 주문, 회원 파트로 나누어서 일정을 유연하게 관리하였습니다.
- 처음부터 중요도가 있는 파트에 일정을 배분하였습니다.

## 6. 테스트 커버리지
### 북스토어 API 서버 테스트 커버리지
![image](https://github.com/user-attachments/assets/83811ac6-3454-4a35-8b95-5746c96deee9)

### 쿠폰서버 API 테스트 커버리지
![image](https://github.com/user-attachments/assets/aa44e9a0-3e57-43ba-be6a-9f05e905ac44)


## 7. REST API Specification
![스크린샷 2024-07-18 14 55 50](https://github.com/user-attachments/assets/a8970d4d-2180-41f5-b0ec-8317a68d56b0)
- Spring REST DOC을 사용하여 API 명세서를 만든 후 Swagger UI를 사용하였습니다.

## 8. 업무 분담 및 주요기능
## 김병우
### 담당
- 장바구니
    - 비회원, 회원 장바구니 REST API 구축과 UI 구현
    - 쿠키 사용으로 비회원, 회원의 정보를 DB 에 저장하여 기능 개선.
    - 캐쉬, DB 두개의 장점을 갖기 위해 Redis 를 DB 와 동기화하여 TPS 약 50% 증가
- 주문
    - 회원,비회원 주문 프로세스 REST API 구축과 UI 구현
    - 정확한 주소를 고객에게 제공하기 위해 행안부 주소도로명 API를 추가하여 배송지를 정확한 주소로 추가할수 있게 구현하였습니다.
    - Toss Payment 와 주문 프로세스를 한 트랜잭션에 묶어 주문 프로세스 구현
- 쿠폰
    - 쿠폰 REST API 구축과 UI 구현
    - 높은 트래픽을 안정적으로 처리하기 위해 쿠폰 발급에 RabbitMQ 를 도입하여 오류 0%로 줄이고 TPS 약 10% 증가
    - JPA 장점과 실패 시 오류 로그 출력을 위해 Spring Batch 를 사용하여 쿠폰 만료 알림 구현
    - 쿠폰 REST API 설계와 UI 구현하였습니다.
- 포인트
    - 포인트 REST API 구축과 UI 구현하였습니다.
    - 포인트 정책 REST API 구축과 UI 구현하였습니다.
- 인프라
    - Client Side 로드밸런싱을 하기위해 OpenFeign 을 사용하여 각 서버에 효율적으로 접근하도록 네트워크 설계
    - Gateway 가 각 서버를 효율적으로 찾아가기 위해 Spring Eureka 를 사용하여 서버의 내부 정보를 캐싱하여 네트워크 설계

## 김은비
### 담당
- 카테고리 (CRUD)
    - 2단계 이상 자기 참조 카테고리 구현
    - 메인 페이지 카테고리 전체 조회 UI 구현
- 도서
    - 도서 페이지 조회/정렬 (이름순, 조회순, 좋아요순, 가격순) - 내림차순/오름차순 구현
    - 메인/도서 상세 페이지 UI 구현
- 리뷰 (CRUD)
    - 등록 : 자신이 구매한 도서에서만 작성이 가능하도록 구현 (toast ui 이용, 이미지 등록 가능)
    - 삭제 : 관리자 권한 확인/삭제 사유 적은 후 soft delete -> 각종 조회 시 리뷰 상태가 delete인 경우 조회에서 제외되도록 구현
    - 조회 : 마이페이지에서 자신이 작성한 리뷰 페이지/ 도서 상세 페이지에서 해당 리뷰 페이지 조회/정렬(추천순/날짜순)되도록 구현
- 도서-좋아요 (CRD)
- 리뷰-좋아요 (CRD) : 자신이 작성한 리뷰에서는 좋아요 추가되지 않도록 구현
- 리뷰-댓글 (CRD)
- 인프라
    - Git, GitAction, Docker로 네트워크를 설계 프로젝트의 유지보수성 높임
- Spring cache
    - redis cache를 이용해서 메인 페이지(도서 조회/카테고리 조회) 성능 약 96% 개선 (5000개의 요청이 갔을 때 6092ms -> 240ms)
- 프론트
    - 타임리프 레이아웃(header, footer, sidebar, login_check.js) 설정
 
## 오연수
### 담당
- 회원
    - 멤버 정보 수정 및 삭제 구현
    - 멤버 인증 정보 관련 API 작성
    - JWT, Redis 활용한 인증 시스템 구현
    - 로그인 및 로그아웃 기능 구현
 - 스프링 게이트웨이
    - 클라이언트 요청을 각 서비스로 라우팅하고, JWT를 검증하여 유효한 요청만 전달
## 유지아
### 담당
- 회원
    - 회원가입 및 탈퇴 구현
    - 로그아웃 구현
    - 멤버 정보 조회 구현
    - 멤버 정보 삭제 조회
    - Payco 인증 구현
    - 휴면 상태 인증번호로 인증 후 해지 구현
- 스프링배치
    - 회원 구매 비용 주기적으로 확인하여 등급변경 구현
    - 회원 마지막 접속일 주기적으로 확인하여 휴면 상태 변경

## 정주혁
### 담당
- 주문
    - 주문 내역 조회 (회원, 비회원) UI 구현
    - 주문 내역 상태 변환 구현 
    - 주문 환불 구현 및 결제 취소 구현 및 UI 구현
    - 회원 주문 및 장바구니 서비스 구현
- 도서
    - 북 태그 서비스 구현
- ERD
    - 관리 및 보수
  
## 한민기
### 담당
- 도서
    - 도서 REST API 구축
    - 도서 설명에 Toast UI를 적용시켜 다양한 방식의 도서 설명 활용성을 증가
    - 도서 이미지를 object storage에 저장하여 유지보수를 높임
    - 알라딘 API를 통해 도서 등록 기능 구현
- 검색
    - 도서 검색 REST API 구축
    - Elastic Search 도입으로 2.7배 속도 개선
    - Elastic Search nori, ngram을 적용하여 Full Text Search 구현
    - Elastic Search 사전 정의어, 동의어, 금지어 구현
- 스프링 배치
    - 배치 서버를 통해 Elastic Search 데이터 입력 및 백업 데이터 생성
- front
    - Spring Security를 사용하여 회원의 인증, 인가 확인 기능 구현
- 기타 편의기능
    - Log & Crash Search 적용하여 로그 수집
    - Key Manager 적용하여 정보 보안
    - Rest Doc, Swagger 사용하여 API 명세서 적용

## 기술
- Spring <br>
![Spring](https://img.shields.io/badge/Spring-6DB33F?style=flat&logo=spring&logoColor=white)
![Spring Boot](https://img.shields.io/badge/SpringBoot-6DB33F?style=flat&logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/SpringSecurity-6DB33F?style=flat&logo=springsecurity&logoColor=white)
![Spring Session](https://img.shields.io/badge/SpringSession-6DB33F?style=flat&logo=spring&logoColor=white)
![Spring Batch](https://img.shields.io/badge/SpringBatch-6DB33F?style=flat&logo=spring&logoColor=white)
![Spring Cloud](https://img.shields.io/badge/SpringCloud-6DB33F?style=flat&logo=spring&logoColor=white)

- DB <br>
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat&logo=redis&logoColor=white)
![Redis](https://img.shields.io/badge/MySql-4479A1?style=flat&logo=mysql&logoColor=white)

- CI/CD <br>
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat&logo=Jenkins&logoColor=white)
![Github Actions](https://img.shields.io/badge/GithubActions-2088FF?style=flat&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=Docker&logoColor=white)
![iCloud](https://img.shields.io/badge/NHNCloud-3693F3?style=flat&logo=icloud&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat&logo=nginx&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=flat&logo=Ubuntu&logoColor=white)

- Search <br>
![Elastic](https://img.shields.io/badge/Elastic-005571?style=flat&logo=Elastic&logoColor=white)
![Elastic Stack](https://img.shields.io/badge/ElasticStack-005571?style=flat&logo=elasticstack&logoColor=white)
![Elastic Search](https://img.shields.io/badge/ElasticStack-005571?style=flat&logo=elasticsearch&logoColor=white)

- 그 외 기술 <br>
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=HTML5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=CSS3&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=CSS3&logoColor=white)
![JAVA](https://img.shields.io/badge/JAVA-007396?style=flat&logo=OpenJDK&logoColor=white)
![Hibernate](https://img.shields.io/badge/Hibernate-59666C?style=flat&logo=Hibernate&logoColor=white)
![JPA](https://img.shields.io/badge/JPA-59666C?style=flat&logo=Hibernate&logoColor=white)
![QueryDsl](https://img.shields.io/badge/QueryDsl-59666C?style=flat&logo=Hibernate&logoColor=white) <br>
![SonarLint](https://img.shields.io/badge/SonarLint-CB2029?style=flat&logo=SonarLint&logoColor=white)
![SonarQube](https://img.shields.io/badge/SonarQube-4E9BCD?style=flat&logo=SonarQube&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat&logo=jsonwebtokens&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat&logo=RabbitMQ&logoColor=white)
![ApacheMaven](https://img.shields.io/badge/ApacheMaven-C71A36?style=flat&logo=ApacheMaven&logoColor=white)
![Toss Payments](https://img.shields.io/badge/TossPayments-0085CA?style=flat&logo=contactlesspayment&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=flat&logo=swagger&logoColor=white)
