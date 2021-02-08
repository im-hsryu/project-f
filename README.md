# O

## O

## 0000 - 제안 

## 1000 - Initialize
### 스크럼 팀 구성

### 스크럼 환경 구성

### 외부 아키텍처 정의 및 구축

((1)) 표준 외부 아키텍처 구성 내역 설명

((2)) Spring Cloud (Open source 기반)

Spring Cloud Eureka : https://sabarada.tistory.com/61?category=822738, https://sabarada.tistory.com/62

Spring Cloud Ribbon : https://sabarada.tistory.com/54?category=822738

Spring Cloud Gateway : https://eblo.tistory.com/69

Security (OAuth 2.0)

Spring Cloud Config : 

Resilience4j (써킷브레이커, 재시도)

Tracing & Monitoring

분산 추적 (Spring Cloud Sluce, zipkin with RabbitMQ)

k8s

Log 중앙화 (ELK, EFK), elastic search, Log trace, Kibana

Microservies Monitoring (프로메테우스, 그라파나), 그라파타 대시보드 개발, 그라파타 경고

Spring Cloud Feign : https://sabarada.tistory.com/115?category=822738

Spring Cloud Feign with Hystrix : https://sabarada.tistory.com/118?category=822738

Service Mesh (istio)



Kong

www.getting.org

docker 이미지 오해 kong 설치하기 (https://docs.konghq.com/install/docker/)

kong 실행하기

kong-dashboard 프로젝트 설치하기 (https://github.com/PGBI/kong-dashboard)

Kong server에 api 등록



### 내부 아키텍처 정의

Application 내부 아키텍처 구성 컨셉 설명 (Layered ~, Hexagonal ~)

서비스 모델링 & 구현에서 실제 구성해보기

### 개발환경 구축

개인 PC에 환경 구성하고, 설치/설정 결과 확인

JDK, STS, Maven, Lombok, swagger or postman, JUnit, ...

H2DB, MySQL, HeidiSQL 

SonarQube(static analysis), JaCoCo(Test coverage)


### 마이크로서비스 도출

아키텍처와 마이크로서비스 설계 개요

목적 / 장점

과제

서비스 분리

비즈니스 능력에 따른 분리 : 기능별로 분리 (기존 기능목록에서 level 2 or 3을 지정)

서브도메인에 의한 분리 : DDD의 sub-domain 기반으로 서비스 정의, sub-domain 안정적(모듈화), 응집성, 느슨한 결합, 어떻게 식별? 기능 이해, 비즈니스 이해, 조직구조 분석 등 다양한 영역 검토해서 식별 (조직구조 
→ 조직의 여러 그룹이 하위 도메인에 해당, 도메인 모델-도메인 객체)

독립적 운영될 수 있는 단위로 분리 : 다른 서비스의 응답 기다리지 않고 자체 동작 또는 동기 요청에 응답할 수 있는 단위의 서비스로 구성, 가용성 낮아지므로 메시지(이벤트)로 결과적 일관성 맞춤 → cqrl, saga 과다 사용
으로 인한 복잡도 증가

조직구성에 따른 분리 : 아키텍처가 조직구성 반영(콘웨이), 팀/서비스는 각자 자율적으로 동작, 각자 소유, 타 서비스/팀과 느슨한 결함, 문제는 팀이 최종사용자와 매핑안될 수 있음,데이테베이스 문제

서비스 당 데이터베이스 - good, 공유 데이터베이스 - refactoring 해야 함

transaction - eventual persistency, 보상 트랜젝션서비스간 연동

통신

sync

async

추가적으로 할 일

Communication : RestAPI, Messaging

CI / CDTest

Unit Test, API Test, Integration Test, Performance TestMonitoring

Health check, logging (중앙화, 집계...ELK)

모니터링 : 서비스 메트릭 수집 (CPU 부하, 응답시간, 오류 수, 서비스 사용량 등)

Docker / k8sOrg

커뮤니케이션 구조 (콘웨이)

마이크로서비스 도출 워크샵

Big Picture

Core Process

Sub-domain

Bounded Context

(개발 일정, 역량, 운영 환경 고려, As-Is 있는 경우 논리-ERD, 조직 구성 등 추가 고려) Microservice 도출

Service Spec 정의

Product Backlog 도출 (Optional (question) )

Service Spec 정의

API, Data, User story, Risk, UI schetch, ...

전략적 설계 전체를 www.miro.com 에 정리 (templete)



## 2000 - Planning

Release Planning

일감 크기 추정

품질/소통 Planning

테스트 계획 수립

(Optional) 데이터 이행 계획 수립

## 3000 - Executing & Control

### Release Planning

### Sprint Planning

### Backend 설계

도메인 모델링 vs 데이터베이스 모델링

Key Concept

Domain Modeling

VoPC

Context Map

Service Spec


### Backend 구현

Sprint boot Project 생성

Microservice 패키지 구조 생성

Business Logic Layer 구성

Data Access Layer 구성: JPA

Presentation Layer 구성

API 명세/문서화, Swagger 설정

API Test : 리엑티브 마이크로서비스 개발, 논블로킹 동기 API, 이벤트 기반 비동기 서비스, 논블로킹 동기 REST API 개발

MySQL로 저장소 변경

MariaDB로 저장소 변경

업무 기능 추가 후 위의 개발 순서 반복

### UI 설계

### Frontend 구현

React, Vue, Timeleaf

React, Vue 유사함, 비즈니스와 환경에 적합한 것 선택하는 것이 좋음

기존 서비스에서 개선 : Vue, 컴포넌트 재사용과 관리의 수월함, 참고할 개발 레퍼런스가 중요하고 대규모 서비스를 운영 : React 를 선택하는 것이 국내외 개발 블로그와 커뮤니티의 추세임

마이크로서비스 개발 (Backend)

Unit Test

### 지속적 통합 / 지속적 배포

### Sprint 리뷰

### 회고

### 성과측정/분석

## 4000 - Test & Release

### 통합 테스트

### 성능 테스트

### 데이터 이행

### 릴리즈

## 운영

### 모니터링


