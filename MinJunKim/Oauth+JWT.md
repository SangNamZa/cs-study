# OAuth(Open Authorization)

외부서비스(우리가 만들고 있는 서비스)의 인증 및 권한(접근할 수 있는 데이터가 다름)부여를 관리하기 위한 프로토콜(여기서 프로토콜은 규격. google, naver 등은 OAuth라는 규격에 맞춰 인증, 권한을 대행관리 함). 인증(Authentication)과 인가(Authorization)를 포함하는데 인가에 더 초점.

## OAuth 2.0 4가지 인증 방식
1) Authorization Code Grant : 가장 많이 쓰임 / 권한 부여 승인 코드 방식
2) Implicit Grant 암묵적 승인 방식
3) Resource Owner Password Credentials Grant 자원소유자 자격증명 승인 방식
4) Client Credentials Grant 클라이언트 자격증명 승인 방식

## OAuth 2.0 구성 요소
- Resource Owner : 실제로 앱을 활용하는 사용자. ex) 나
- Client Application : 보호된 자원을 사용하려고 접근 요청하는 애플리케이션. 우리가 사용하고자 하는 애플리케이션.
- Authorization Server : 권한(인증, 인가)을 관리하는 서버. Access Token, Refresh Token을 발급, 재발금 함. ex) PAYCO 인증 서비스
- Resource Server : OAuth 관리 서버의 자체 API. OAuth를 통해 인증, 인가를 제공하는 서버. 이름, 이메일 등 자원을 제공한다. ex) PAYCO API 서비스
<br />
Resource Server 와 Authorization Server는 같은 소속이다.

### Authorization Code Grant 권한 부여 승인 코드 방식
<img src='https://github.com/SangHyunGil/Blog/blob/master/img/oauth2jwt/2.PNG?raw=true' />
<img src='https://github.com/SangHyunGil/Blog/blob/master/img/oauth2jwt/3.PNG?raw=true' />


### OAuth 2.0 단점
토큰 유효기간이 짧으면 로그인 자주하는 번거로움, 길면 토큰 탈취 시 보안에 취약. 유효기간이 짧은 access token에는 사용자의 디테일한 정보가 담기고, 유효기간이 긴 refresh token에는 access token을 재발급해주는 역할만함. 서버가 Access Token의 유효성과 권한을 확인하기 위해 서버에 계속적으로 요청하여 서버의 부하로 이어질 수 있다. 이를 해결하기 위해 JWT 기반 인증 방식이 사용됨. 

## JWT(Json Web Token) : Json 포맷을 이용하여 사용자에 대한 속성을 저장하는 Claim(토큰에 저장된 정보들) 기반의 Web Token.

사용자의 정보를 안전하게 자체적으로 담고 있어서 토큰 자체를 정보로 사용함. 한번 인증 후에는 JWT를 활용하여 자체적으로 정보가 맞는지 확인하여 만료전까지 계속 사용.
토큰이 세션 대신 사용되는 이유는 stateless 해서 확장에 용이하기 때문. 토큰은 로그인이 유지되는 것 같은거지, 실제로 로그인을 유지하는게 아니다. 클라이언트가 access token을 저장해두고, 요청 때 마다 보내는 방식이라서, access token을 가지고 있다면 로그아웃을 했더라도 로그인 된 상태처럼 행동한다.

### JWT 구성 (Header, Payload, Signature)
- Header : JWT를 어떻게 검증(Verify)하는가 설정. typ는 토큰의 타입을 지정, alg는 Signature(서명) 부분에서 사용하는 알고리즘(HS256, RSA 등등)
- PayLoad : 토큰에 저장된 정보들(3가지 종류의 클레임 : 등록된 클레임, 공개 클레임, 비공개 클레임)이 Json 형태로 여러 정보가 담겨진다.
- Signature : 토큰을 인코딩하거나 유효성 검증을 할 때 사용되는 고유한 암호화 코드.

## 과정
<img src='https://velog.velcdn.com/images%2Fmax9106%2Fpost%2F5620524a-4359-4abd-b90c-07b65359b3ca%2F%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202021-07-12%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%204.16.43.png' />

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
