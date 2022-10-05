# Event Loop
### 싱글 스레드 JavaScript
JS는 싱글 스레드이지만 이는 브라우저를 통해 실행되게 되어있고, 브라우저 덕분에 우리가 보기에는 동시성을 갖는 작업을 하게된다.<br />
Call Stack - WebAPIs - Callback Queue 의 빠른 연계와 순차적인 작업 덕분에 비동기 함수와 동기함수들이 동시에 동작하는 듯이 느껴지게된다.<br />
모든 건 순차적으로 하나의 스레드(콜 스택) 안에서 돌아간다.<br />

<img src='https://miro.medium.com/max/1600/1*iHhUyO4DliDwa6x_cO5E3A.gif' width='100%' />
이 과정 전체가 브라우저의 구조이다.<br />
자바스크립트 엔진은 Memory Heap 과 Call Stack으로 이루어져있다.

#### Heap
힙은 메모리 할당이 일어나는 부분이다(변수, 객체 등이 저장되는 일종의 창고)<br />

#### Stack
- 함수가 호출되는 순서대로 쌓이느 스택
- 함수 실행 시 호출 스택에 해당 함수가 들어감
- 함수 실행이 끝나면 호출 스택의 맨 위에 있는 해당 함수가 사라짐

#### 콜백 함수
- 다른 함수의 인자로 넘겨지는 함수이다.
- 동기 콜백의 경우 호추 즉시 실행되고, 비동기 콜백의 경우 조건을 만족했을 때 실행된다.


과정 설명 참고 블로그<br />
https://blog.sessionstack.com/how-javascript-works-event-loop-and-the-rise-of-async-programming-5-ways-to-better-coding-with-2f077c4438b5

1.실행될 함수가 차례로 스택에 쌓인 후 실행되면 바로 사라진다.<br />
2.쌓일 때 WebAPI를 사용하게되면 그부분으로 넘어간다.(그러고 스택에서 사라지고, 다음 함수가 쌓인다)<br />
3.setTimeout 처럼 그 과정이 실행되면, callback 함수가 callback queue에 줄 선다.<br />
4.callback queue에 줄 선 콜백함수들을 event loop가 스택이 비엇는지 주시하다가 비면 스택으로 넣어준다.<br />
5.promise의 경우 다르 방식으로 작동하는 점 참고
