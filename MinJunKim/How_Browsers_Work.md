# 웹 브라우저의 작동 원리
<br/>

## 브라우저란?

웹 브라우저는 서버에게 필요한 자원(웹 페이지, 이미지, 동영상 등)를 요청하면 서버가 응답한 자원을 전송받고,    
HTML, CSS, Javascript 언어를 브라우저가 해석하여 내용을 화면에 보여주는 응용 소프트웨어이다.
<br/>
<br/>
<br/>
 
### 브라우저의 구조   
<img src="https://user-images.githubusercontent.com/101058125/187609484-200283e5-0a90-49a6-bb3e-a72fd8659f86.png" width="40%" height="30%" title="px(픽셀) 크기 설정" alt=""></img> 

1.사용자 인터페이스
사용자가 접근하는 영역으로, 주소 표시줄, 이전/다음/홈버튼/새로고침 버튼 등 브라우저 프로그램 자체의 GUI를 구성하는 부분
<br/>
<br/>

2.브라우저 엔진
- 사용자 인터페이스와 렌더링 엔진 사이의 동작을 제어한다.
- 자료 저장소(Data Storage)를 참조하며 로컬에 데이터를 쓰고 읽으면서 다양한 작업을 한다.
<br/>

3.렌더링 엔진
- 요청한 콘텐츠를 화면에 출력하는 역할
- HTML, CSS 등을 파싱(데이터를 가공하고 추출하여 불러오는)하여 최종적으로 화면에 그림
<br/>

4.통신 Networking
- http 요청을 하며 네트워크를 호출
<br/>

5.자바스크립트 해석기 JS Engine
- javascript 코드를 해석하고 실행
<br/>

6.UI Backend
- select, input 등 기본적인 위젯을 그리는 인터페이스. 플랫폼에서 명시하지 않은 일반적인 인터페이스로서, OS 사용자 인터페이스 체계를 사용.
<br/>

7.자료 저장소 Data Storage
- Local Storage, Indexed DB, 쿠키 등 브라우저 메모리를 활용하여 local에 data를 저장하는 영역
<br/>
<br/>
<br/>


### <렌더링 엔진의 동작 원리>    
<img src="https://user-images.githubusercontent.com/101058125/187609676-29d8b459-b8e8-4e76-9c97-1d5d331df2f9.png" width="60%" height="40%" title="px(픽셀) 크기 설정" alt=""></img>   
###### 이는 렌더링 엔진의 크게 나눈 동작 과정으로, 각 단계에 해당하는 설명을 더 세부적이게 나누어 아래에 할 예정
<br/>
<br/>


<img src="https://user-images.githubusercontent.com/101058125/187609692-7b19335e-1afa-49ae-8bbf-788ef2fc8d2f.png" width="80%" height="60%" title="px(픽셀) 크기 설정" alt=""></img>   
###### 웹킷 엔진(크롬, 사파리용 렌더링 엔진)의 세부적인 과정 예시


① 브라우저는 서버로부터 HTML 문서를 모두 전달 받는다. 렌더링 엔진은 전달받은 *HTML 문서를 파싱하여(브라우저가 코드를 이해하고 사용할 수 있는 구조로 변환하여) *DOM 트리를 구축한다.   
② 외부 CSS 파일과 함께 포함된 스타일 요소를 파싱한다.    
③ DOM 트리와 ②의 결과물(CSSOM)을 합쳐 *렌더 트리를 구축한다.   
④ 렌더 트리의 각 *노드에 대해서 화면 상에서 어디에 배치할 지 결정한다.    
⑤ UI백엔드에서 렌더 트리를 그리게 되고, 화면에 우리가 볼 수 있도록 출력된다.   
<br/>
<br/>


① HTML 파싱 후 DOM 트리 구축
*파싱
- 문서 파싱: 브라우저가 코드를 이해하고 사용할 수 있는 구조로 변환하는 것을 의미. 
    - 파싱 결과는 보통 문서 구조를 나타내는 *노드 트리인데 파싱 트리(parse tree) 또는 문법 트리(syntax tree)라고 부른다.
    - 노드 트리 : 노드는 트리 구조로 정렬되기도 한다. 노드는 하나의 자료 구조에 포함된 정보를 표현한다. 이 노드들은 값이나 조건을 포함할 수 있으며 다른 독립된 자료 구조의 역할을 할 가능성이 있다.   
<br/>

￼![helloworld-59361-5](https://user-images.githubusercontent.com/101058125/187609714-ea1469f9-4df3-4994-908b-f8f1fb809166.png).  

###### 수학 표현식을 파싱한 트리 노드 예시


*DOM(Document Object Model)
- 크게는 웹 브라우저가 HTML 페이지를 인식하는 방식을 의미하며, 좁게는 document 객체와 관련된 객체의 집합이다
    - Document Object란 <html>, <body> 등 html 문서들의 태그들을 Javascript가 이용할 수 있는 객체(object)로 만든 것
    - DOM은 웹 페이지를 스크립트 또는 프로그래밍 언어들에서 사용될 수 있게 연결시켜주는 역할을 담당
    - 문서의 모든 element - 전체 문서, 헤드, 문서 안의 table, table header, table cell 안의 text - 는 문서를 위한 document object model 의 한 부분이다. 

*DOM 트리
- DOM을 트리 구조화 시킨 것

<img src="https://user-images.githubusercontent.com/101058125/187609738-de8abf9b-599b-4662-958f-d3771c934481.png" width="40%" height="30%" title="px(픽셀) 크기 설정" alt=""></img>  
 <br/>



② 외부 CSS 파일과 함께 포함된 스타일 요소를 파싱한다 : CSSOM(CSS Object Model) 생성
- ①에서 HTML로 DOM을 생성하는 과정처럼 CSS에도 이루어지는 과정이다
- 브라우저가 이해하고 처리할 수 있는 형식(Style Rules)로 변환된다 
<br/>



③ DOM 트리와 ②의 결과물(CSSOM)을 합쳐 *렌더 트리를 구축한다. 
- DOM(내용을 구성)과 CSSOM(스타일을 구성)이 합쳐지는 과정 진행한다.
- DOM + CSSOM => Render Tree(브라우저가 앞의 두가지를 병합하여 화면에 픽셀을 렌더링 하기 위한 마지막 단계)
 <br/>


*Render Tree 구축 과정   
1.DOM 트리를 읽으며 각 노드들에 표시를한다.   
2.표시된 노드들에 CSSOM 스타일 규칙을 알맞게 적용한다.    
3.표시된 노드들을 콘텐츠와 스타일이 적용된 상태를 내보낸다.   
<br/>


④ 렌더 트리의 각 *노드에 대해서 화면 상에서 어디에 배치할 지 결정한다.
- 객체들에 위치와 크기를 결정해주어 화면 어디에 배치될 지 결정

⑤ UI백엔드에서 렌더 트리를 그리게 되고, 화면에 우리가 볼 수 있도록 출력된다.
- 렌더 트리의 각 노드들이 화면의 픽셀로 나타나고, 렌더 트리를 그리는 과정이 완료되면 화면에 우리가 보는 콘텐츠가 표현되는 것이다

 <br/>
 <br/>
 <br/>
 
참고 : https://d2.naver.com/helloworld/59361
