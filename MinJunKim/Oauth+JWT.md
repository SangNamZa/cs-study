# OAuth(Open Authorization)

인증을 위한 프로토콜. 인증(Authentication)과 인가(Authorization)를 포함하는데 인가에 더 초점.

## OAuth 2.0 구성 요소
- Resource Owner : 사용자. 사람 또는 Application 자체. ex) 나
- Client Application : 사용자가 사용하는 서비스 앱. 서버, 데탑 등 기기들. ex) velog
- Resource Server : OAuth를 통해 인증, 인가를 제공하는 서버. 이름, 이메일 등 자원을 제공한다. ex) google, naver
- Authorization Server : OAuth를 통해 인증, 인가를 제공하는 서버. 토큰을 발급함. ex) google, naver

Resource Server 와 Authorization Server는 같은 소속이다.

## OAuth 2.0 4가지 인증 방식
1) Authorization Code Grant
2) Implicit Grant
3) Resource Owner Password Credentials Grant
4) Client Credentials Grant

## JWT

## 프론트엔드 파트
- github OAuth 서버로 github 로그인 요청 후, Authorization code 발급 받아, 백엔드에 전달
- 백엔드에서 응답 받은 access token, refresh token 저장해두기
- 권한이 필요한 요청마다 Authorization 헤더에 access token 같이 보내주기
- access token이 만료되었다면, refresh token 보내서 갱신하기(프론트에서 요청 날릴 때 access token이 만료됨을 미리 판별하여 갱신 요청을 보낼 수 있음)
- refresh token 만료 기간이 7일 이내면, refresh token 재발급 요청

## 백엔드 파트
- Authorization code로 github OAuth 서버에 토큰 요청
(로그인 할 때 이외에 OAuth 서버와 통신이 필요한 경우 발급 받은 토큰 저장해야 할듯)
- Access token으로 이름, 이메일, 프로필 URL 정보 요청
- db에 존재하지 않는 유저라면, 새로 등록. db에 존재하는 유저라면 정보 업데이트
- 유저의 primary key 값으로 JWT 토큰(access token & refresh token) 생성. 일반적으로 access token은 한 시간, refresh token은 2주로 생성(본인 애플리케이션에 맞게 변경하여 사용)
- refresh token은 DB나 Redis에 저장
- 유저 정보, access token, refresh token 프론트로 전달
- access token 만료시 refresh token 검증 후, 재발급
