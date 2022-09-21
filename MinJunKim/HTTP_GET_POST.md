# HTTP GET POST

## HTTP
http에서 프로토콜이란 특정 기기 간에 데이터를 주고받기 위해 정의한 상호 간의 규칙이다.

## HTTP Method
URL을 이용하여 서버에 특정 데이터를 요청하면서 특정 동작을 수행하고자 할 때 HTTP 요청 메서드(Http Request Methods)를 이용한다.

* GET : 존재하는 자원에 대한 요청
* POST : 새로운 자원을 생성
* PUT : 존재하는 자원에 대한 변경
* DELETE : 존재하는 자원에 대한 삭제

## HTTP GET / POST
### GET
주로 데이터를 읽거나 검색할 때에 사용   
데이터를 읽을 때만 사용되고 수정할 때는 사용하지 않는다 -> 데이터의 변형 위험이 없다   
모든 필요한 데이터를 URL에 포함하여 요청   
data는 URL로 인코딩되어 action URL에 query string parameters로 전달=데이터 길이 제한,파라미터들은 URL의 일부분이기 때문에 브라우저 히스토리에 남음 -> 보안을 약하게 만듦.  
URL로 인코딩되어서 북마크 가능   
<img src="https://velog.velcdn.com/images%2Fpear%2Fpost%2Faee93259-5dee-4820-b971-4db7c82d78a1%2FScreen%20Shot%202020-08-30%20at%2010.12.17%20PM.png" width="60%" height="40%" alt=""></img>

:쿼리스트링
### POST
주로 새로운 리소스를 생성할 때 사용   
POST 요청을 반복해서 했을 때 항상 같은 결과물이 나오는 것을 보장하지 않음   
POST 요청은 클라이언트에서 서버로 전송할 때 추가적인 데이터를 body에 포함=데이터 길이 제한 없음   
data는 HTTP request의 message body에 나타남    
POST는 파라미터들이 브라우저 히스토리나 서버 로그에 저장되지 않기 때문에 GET에 비해 안전



|                | GET       | POST | 
| -------------- | ---------- | ------ | 
| 캐시            | O | X |
| 브라우저 기록     | O | X |
| 북마크 추가      | O | X |
| 데이터 길이 제한  | O | X |
| HTTP 응답 코드	| 200(Ok)	 | 201(Created)|
|언제 주로 사용하는가?	| 리소스 요청	 | 리소스 생성 |
| 리소스 전달 방식	| 쿼리스트링	 | HTTP Body |
| idempotent*| O | X |
| 보안(상대적으로)| 위험 | 안전 |


*idempotent : 멱등성 = 연산으 여러 번 적용하더라도 결과가 달라지지 않는 성질 -> 캐시 가능 여부 달라짐

