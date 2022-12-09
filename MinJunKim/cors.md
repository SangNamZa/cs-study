# CORS : Cross-Origin Resource Sharing
브라우저에서 다른 출처의 리소스를 공유하는 방법

<img src='https://user-images.githubusercontent.com/45661217/147995359-52b52ffc-2443-4071-8364-d782819f730b.png' />
=> Origin(출처) : URL 구조 중에서 protocal, host, port를 합친 것

SOP : Same-Origin Policy 동일 출처 정책
=> 브라우저가 다른 출처의 리소스 접근을 금지 : 외부 리소스를 사용 가능한 SOP의 예외가 CORS

CORS 에러 해결 방법
서버에서 Access-Control-Allow-Origin 헤더를 포함한 응답을 보라우저에 보내는 방식으로 해결할 수 있기에, 프론트에서 CORS에러를 접하면 서버에 CORS 해결을 위한 응답 헤더를 포함하도록 요청해야함
서버에서는 라이브러리를 사용하면 간단하게 CORS 해결 가능
프론트엔드와 백엔드 사이에 프록시 서버를 두어서 해결도 가능. 개발 환경에서 해결할 경우 webpack dev server 등의 라이브러리를 사용해 프록시 설정 가능

CORS 동작원리 2가지

1.Simple request
서버에 API를 요청하고, 서버에서는 Access-Control-Allow-Origin 헤더를 포함한 응답을 브라우저에 본낸다. 브라우저는 이 헤더를 확인하고 CORS 동작을 수행 여부 판단.

2. Preflight request
실제 리소스를 요청하기 전에 예비요청으로 OPTIONS라는 메서드를 통해 실제 요청을 전송할지 판단하고서 본요청을 보낸다.
