# 배당금 프로젝트 개요 🌿
해당 프로젝트는 미국 주식의 배당금 정보(Yahoo Finance)를 제공하는 API 서비스를 개발하는 것을 목표로 합니다. <br>
Spring Boot, JPA, H2, Redis, Jsoup을 사용하여 구현되었습니다.

<br>

## 프로젝트 설정 <br>
- Spring Boot 2.5.6  <br>
- Java 11  <br>
- Gradle  <br>
- JPA (Hibernate)  <br>
- H2  <br>
- Jsoup  <br>

<br>

## 최종 구현 API 목록 <br>
✅ GET - /finance/dividend/{companyName}
- 설명: 회사 이름을 입력받아 해당 회사의 메타 정보와 배당금 정보를 반환
- 오류 처리: 잘못된 회사명이 입력으로 들어온 경우 400 상태 코드와 에러 메시지를 반환

<br>

✅ GET - /company/autocomplete
- 설명: 자동완성 기능을 위한 API로, 검색하고자 하는 prefix를 입력받아 해당 prefix로 검색되는 회사명 리스트 중 10개를 반환

<br>

✅ GET - /company
- 설명: 서비스에서 관리하고 있는 모든 회사 목록을 반환 
- 반환 결과: Page 인터페이스 형태로 반환

<br>

✅ POST - /company
- 설명: 새로운 회사 정보를 추가 
- 입력: 추가하고자 하는 회사의 ticker를 입력받아 해당 회사의 정보를 스크래핑하고 저장 
- 오류 처리: 이미 보유하고 있는 회사 정보일 경우 400 상태 코드와 적절한 에러 메시지를 반환. 존재하지 않는 회사 ticker일 경우, 400 상태 코드와 적절한 에러 메시지를 반환

<br>

✅ DELETE - /company/{ticker}
- 설명: ticker에 해당하는 회사 정보를 삭제
- 요구사항: 삭제 시 회사의 배당금 정보와 캐시도 모두 삭제되어야 함.

<br>

✅ POST - /auth/signup
- 설명: 회원가입 API 
- 요구사항: 중복 ID는 허용하지 않으며, 패스워드는 암호화된 형태로 저장되어야 함.

<br>

✅ POST - /auth/signin
- 설명: 로그인 API
- 요구사항: 회원가입이 되어있고, 아이디/패스워드 정보가 옳은 경우 JWT를 발급

<br>
