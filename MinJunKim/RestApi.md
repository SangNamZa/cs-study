# REST API (Representational State Transfer Application Programming Interfaces)
<br />
<br />

## API란?
API는 정의 및 프로토콜 집합을 사용하여 두 소프트웨어 구성 요소가 서로 통신할 수 있게 하는 메커니즘이다.   
API 아키텍처는 일반적으로 요청을 보내는 애플리케이션인 클라이언트와 응답을 보내는 애플리케이션인 서버로 구성된다.   
API 의 종류로는 SOAP API, RPC API, Websocket API, REST API 가 있다.   
이 중에서 REST API는 오늘날 웹에서 가자 많이 사용되고 유연한 API이다.   
서버 프로그램의 다양한 브라우저와 디바이스에서도 통신으 해야하게 되었고, 멀티 플랫폼들을 지원해주기 위해 자원에 대한 아키텍처를 세우고 이용하는 방법이 필요했다.

![image](https://user-images.githubusercontent.com/101058125/189017801-14d7030b-f402-492b-9ef5-f02ec792e93f.png)

## REST API란?
웹에서 데이터를 전송하고 처리하는 방법을 정의한 인터페이스.   
HTTP URI를 통해 자원(Resource)을 명시하고,
HTTP Method(POST, GET, PUT, DELETE)를 통해 해당 자원에 대한 CRUD Operation을 적용하는 것을 의미



## REST 구성

![스크린샷 2022-09-08 오후 12 24 22](https://user-images.githubusercontent.com/101058125/189027150-1324a156-7a37-4369-a7fa-a55493135854.png)



#### Request Message의 구성 : start line / headers / body
- start line는 URI와 Verb로 구성된다.
  - URI가 있어서 어디로 접근할지 정해지고,
  - request method verb (CRUD) 로 어떤 요청을 수행할지 정해진다.
 
- headers
  - Accept 부분의 헤더는 어떠한 포맷으로 정보를 받아들일지 정할 수 있고,
  - Authorization 부분의 헤더는 요청을 보낼 권한이 있다고 서버에 알려준다.
 
- body
  - 전달할 가공된 데이터

![스크린샷 2022-09-08 오후 12 33 09](https://user-images.githubusercontent.com/101058125/189028221-dd6f29e6-ac01-410d-816d-fd97a52934b8.png)
#### Response Message : status code / headers / body
- status code 상태 코드가 클라이언트에게 요청 결과를 알려준다.
  - 200번대 = 클라이언트 요청이 성공적으로 수행됨
  - 400번대 = 클라이언트의 요청이 잘못되었다
  - 500번대 = 서버쪽에 오륙 있다

- headers 여기는 서버에 관한 정보가 담겨있다. 

- body가 구성된다. 주로 json 포맷의 data payload 이다.



### REST API의 주된 특징
- Stateless 무상태성
  - 서버가 요청 간에 클라이언트 데이터를 저장하지 않는다. 
  - 서버의 처리 방식에 일관성을 부여하여 부담이 줄고, 서비스의 자유도가 높아진다.
- Layered System 계층화
  - 요청된 정보를 검색하는 데 관련된 서버(보안, 로드 밸런싱 등을 담당)의 각 유형을 클라이언트가 볼 수 없는 계층 구조로 체계화하는 계층화된 시스템.
- Uniform Interface 인터페이스 일관성
  - URI로 지정한 resource에 대해 통일된 인터페이스로 수행
  - http 표준 프로토콜에 따르는 모든 플랫폼에서 사용 가능
