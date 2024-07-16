# 3조업고튀어(3runner)

## 1. 팀원
- 김병우 [helloJosh](https://github.com/helloJosh)
- 김은비
- 유지아
- 정주혁
- 한민기

## 2. ERD
![bookstore (5)](https://github.com/user-attachments/assets/66cd8083-879c-40f7-8f8f-54d12d9cd6de)
- 꾸준히 변경할 때 마다 버전 관리하여 0.04버전이 최종 버전이 되었습니다.

### DB관리자
- 정주혁
- DDL [DDL코드보기]()


## 3. 아키텍처
![systemarchitecture](https://github.com/user-attachments/assets/9bcdfe5c-8550-445d-9eab-74f8fcaef78e)
- 프론트 네트워크와 백 네트워크를 게이트웨이를 통해서만 접근 가능하게 도커 네트워크를 활용하여 설계하였습니다.
- 배포 빈도와 요청이 높은 프론트 서버와 북 스토어 서버는 각각 2개를 만들어 부담을 줄였습니다.

## 4. CI/CD
![cicd](https://github.com/user-attachments/assets/c187ac35-4810-44e9-b39c-572d2c0bbe60)
- 코드가 머지했을 때만 깃 액션이 반응하게 파이프라인을 설계했습니다.
- 프론트, 북스토어 서버는 배포 빈도가 높기 떄문에 스크립트를 작성하여 도커 stats를 활용해 무중단 배포를 구현하였습니다.

## 5. 프로젝트 관리
체계적이고 효율적인 관리를 위해, [Github Project](https://github.com/orgs/nhnacademy-be6-3runner/projects/1)을 활용하여 프로젝트를 진행하였습니다.

### BackLog, RoadMap 활용
![image](https://github.com/user-attachments/assets/ea9ffcef-046d-4db0-9947-bc38295b8bef)
- 매일 9:30에 RoadMap과 BackLog를 활용하여 스크럼 회의를 진행했습니다.

### Scrum
스크럼 스샷
스크럼은 평일, 하루에 한 번씩 진행하였습니다.

### Issue관리
Issue 사항 스샷


### Manage
git flow 전략 스샷

### PR
Pr 전략 스샷

### CodeReview
코드리뷰 전략 스샷

## 6. 일정관리 - WBS
WBS 스샷


## Github Roadmap 관리
주문, 회원, 도서 로 나누어서 일정관리

## BackLog
backlog 관리 스샷

## 테스트 커버리지
Shop 서버의 주요 기능들에 대한 테스트 커버버리지 스샷

## REST API Specification
RestDoc 사용 스샷 및 설명





# 업무 분담 및 주요기능



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
