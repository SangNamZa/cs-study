# CORS : Cross-Origin Resource Sharing
### 브라우저에서 다른 출처의 리소스를 공유하는 방법
<br />
<br />
<br />
<img src='https://user-images.githubusercontent.com/45661217/147995359-52b52ffc-2443-4071-8364-d782819f730b.png' />
=> Origin(출처) : URL 구조 중에서 protocal, host, port를 합친 것 <br />

- https://minjun.github.io/이 뒤에 이것 저것 붙어도 다 같은 출처
- https://minjun.gihub.io:77 : 포트가 달라서 다름, http/https도 프로토콜이 다름, 호스트가 달라도 다른 출처이다
<br />
<br />

## SOP : Same-Origin Policy 동일 출처 정책
=> 브라우저가 다른 출처의 리소스 접근을 금지 : 외부 리소스를 사용 가능한 SOP의 예외가 CORS   
- Same-Origin 서버의 리소스는 사용 가능하지만, Cross-Origin 서버에 있는 이미지나 여러 리소스는 상호작용이 불가능
- XSS, XSRF 등의 보안 취약점을 노린 공격을 방어할 수 있는 점이 SOP의 장점
<br />
<br />

## CORS 동작원리 2가지
- Simple request<br />
=> 서버에 API를 요청하고, 서버에서는 Access-Control-Allow-Origin 헤더를 포함한 응답을 브라우저에 본낸다. 브라우저는 이 헤더를 확인하고 CORS 동작을 수행 여부 판단.
<br />

- Preflight request<br />
=>실제 리소스를 요청하기 전에 예비요청으로 OPTIONS라는 메서드를 통해 실제 요청을 전송할지 판단하고서 본요청을 보낸다.   
예비요청의 HTTP 메소드는 GET이나 POST가 아니고 OPTIONS라는 요청을 사용
<br />
<br />

## CORS 에러 해결 방법
서버에서 Access-Control-Allow-Origin 헤더를 포함한 응답을 보라우저에 보내는 방식으로 해결 가능   
프론트에서 CORS에러를 접하면 서버에 CORS 해결을 위한 응답 헤더를 포함하도록 요청해야함   
서버에서는 라이브러리를 사용하면 간단하게 CORS 해결 가능
프론트엔드와 백엔드 사이에 프록시 서버를 두어서 해결도 가능(개발 환경에서 해결할 경우 webpack dev server 등의 라이브러리를 사용해 프록시 설정 가능)
