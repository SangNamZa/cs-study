# DOM : Document Object Model

서비스들은 웹 브라우저를 바탕으로 실행되는데, 이 브라우저와 관련된 객체들의 집합을 BOM : Browser Object Model 이라고 한다. DOM은 BOM 중에 하나로 문서 객체 모델이다.

문서객체란 <html> 이나 <body> 같은 html문서의 태그들을 javaScript가 이용할 수 있는 객체(object)로 만든 것이다.+model 은 모형, 인식하는 방식이라고 해석 가능하다. 
  
  그래서 DOM이란 넓게는 웹 브라우저가 HTML 페이지를 인식하는 방식 / 좁게는 document 객체들의 집합을 의미한다.
  
### DOM vs HTML
- HTML : 화면에 보이고자 하는 모양과 구조를 문서로 만든 것으로 단순 텍스트로 구성(최초에 화면을 그릴때 사용하는 설계도)
- DOM : HTML 문서의 내용과 구조가 객체 모델로 변화되어 다양한 프로그램에서 사용 가능(설계도를 이용하여 실제로 화면에 나타내지는 인터페이스)
- DOM이 원본 HTML 소스와 다른 경우 : 작성된 HTML 문서가 유효하지 않아 코드를 맞게 교정하는 경우. JS가 동적으로 생성하는 경우
  
### DOM은 tree 구조이다. 대표적으로 HTML 태그를 요소노드(Element Node), 요소 노드 안의 글자들을 텍스트노드(Text Node)라고 부른다.
   
<img src='https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/DOM-model.svg/1200px-DOM-model.svg.png'/>
  
  
### JavaScript로 DOM 생성하기
- 정적으로 생성 : 웹 브라우저가 HTML 페이지에 적혀 있는 태그들을 읽으면 생성되는 것. 단순히 적힌 그대로 문서객체가 생성되는 것.
- 동적으로 생성 : 원래 HTML 페이지에 없던 dom을 js를 이용해서 생성하는 것. 
  
```
  <!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title> 문서객체 모델(DOM)</title >
<script type= "text/javascript">
    window.onload = function(){
       //1. 문서 객체 생성
       var header = document.createElement('h2'); //h2 태그를 생성해주는 것
       var textNode = document.createTextNode('Hello DOM');

       //2. 노드(요소/텍스트)를 연결.
       header.appendChild(textNode);

       //3. body 문서 객체에 header 문서 객체를 추가.
       document.body.appendChild(header);
    };
</script>
</head>
<body>
   <h1 id ="header_1" name= "" >HEADER-1 </h1 >
   <div >
      <h1 id = "header_2">HEADER-2</h1 >
   </div >
   <hr >
   <h1 id = "clock"></h1>
</body>
</html>
```

### DOM API
HTML의 요소들을 js에서 제어하기 위한 명령들
- document.querySelector() : html문서에서 일치하는 요소 중 첫번째를 리턴
- document.querySelectorAll() : 일치하는 선택자 모두 찾아 배열형태로 리턴
- .addEventListner() : 선택한 요소에 이벤트 발생시 지정한 함수 실행
- .classList.add() : 선택한 요소의 클래스에 내용 추가
- .classList.remove() : 선택한 요소의 클래스에서 내용 삭제
- .classList.contains() : 선택한 요소의 클래스에 포함 여부 확인
- forEach() : 배열에서 사용하며, 배열의 아이템들에 반복적으로 함수를 실행
