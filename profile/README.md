# 3조업고튀어(3runner)

## 1. 팀원
- 김병우 [helloJosh](https://github.com/helloJosh)
- 김은비 [ubiies](https://github.com/ubiies)
- 유지아 [lyujia](https://github.com/lyujia)
- 정주혁
- 한민기

## 2. ERD
![bookstore (5)](https://github.com/user-attachments/assets/66cd8083-879c-40f7-8f8f-54d12d9cd6de)
- 꾸준히 변경할 때 마다 버전 관리하여 0.04버전이 최종 버전이 되었습니다.

### DB관리자
- 정주혁
- [DDL코드보기](https://github.com/nhnacademy-be6-3runner/3runner-docs/blob/main/db0.04.sql)


## 3. 아키텍처
![systemarchitecture (1)](https://github.com/user-attachments/assets/7ea1b7aa-2775-46e4-932a-6c8bd73f68bc)
- 프론트 네트워크와 백 네트워크를 게이트웨이를 통해서만 접근 가능하게 도커 네트워크를 활용하여 설계하였습니다.
- 배포 빈도와 요청이 높은 프론트 서버와 북 스토어 서버는 각각 2개를 만들어 부담을 줄였습니다.

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

### BackLog
![image](https://github.com/user-attachments/assets/ea9ffcef-046d-4db0-9947-bc38295b8bef)
- 일정관리와 같이 매일 BackLog도 관리하여 팀원의 스케쥴을 확인하였습니다.

## 6. 테스트 커버리지
Shop 서버의 주요 기능들에 대한 테스트 커버버리지 스샷
### 북스토어 서버 테스트 커버리지
![image](https://github.com/user-attachments/assets/83811ac6-3454-4a35-8b95-5746c96deee9)

### 쿠폰서버 테스트 커버리지
![image](https://github.com/user-attachments/assets/aa44e9a0-3e57-43ba-be6a-9f05e905ac44)


## 7. REST API Specification
RestDoc 사용 스샷 및 설명


## 8. 업무 분담 및 주요기능
## 김병우
### 담당
- 장바구니
    - 비회원, 비회원 장바구니 REST API 구축과 UI 구현
    - 쿠키 사용으로 비회원, 회원의 정보를 DB에 저장하여 사용성 증가
    - Redis를 DB와 동기화하여 장바구니 사용성 증가
- 주문
    - 회원,비회원 주문 프로세스 REST API 구축과 UI 구현
    - Toss Payment와 주문 프로세스를 한 트랜잭션에 묶어 주문 프로세스 구현
    - 주소 등록에 행안부 API 추가하여 주소의 정확성을 높임
- 쿠폰
    - 쿠폰 REST API 구축과 UI 구현
    - 쿠폰 어드민 REST API 구축과 UI 구현
    - 쿠폰 발급에 RabbitMQ를 도입하여 쿠폰서버의 부담을 줄임
- 포인트
    - 포인트 REST API 구축과 UI 구현
- 회원
    - 만료 쿠폰 알림 REST API 구축과 UI 구현
    - 배치서버를 사용하여 쿠폰 만료 알림과 생일 쿠폰 발급
    - RabbitMq 메시지 큐 시스템으로 배치서버의 부담을 줄임
- 인프라
    - Git, GitAction, Docker로 네트워크를 설계 프로젝트의 유지보수성 높임
## 김은비
### 담당
## 유지아
### 담당
- 회원
    - 회원가입 및 탈퇴 구현
    - 로그아웃 구현
    - 멤버 정보 조회 구현
    - 멤버 정보 삭제 조회
    - Payco 인증 구현
    - 휴면 상태 인증번호로 인증 후 해지 구현
-스프링배치
    -회원 구매 비용 주기적으로 확인하여 등급변경 구현
    -회원 마지막 접속일 주기적으로 확인하여 휴면 상태 변경
### 담당
## 정주혁
### 담당
## 한민기
### 담당

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
