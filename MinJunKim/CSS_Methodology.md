# CSS Methodology

대규모 페이지나 협업시 css 작성에 문제가 없도록 SMACSS, BEM, OOCSS 3가지의 방법론이 나타남.<br />
각 방법론은 장단점이 있고, 일부를 결합하여 사용하기도. 절대적인 규칙은 아님.


#### SMACSS (Scalable and Modular Architecture for CSS) : 확장형 모듈식 구조 5가지로 나눔(Base, Layout, Module, State, Theme)
#### BEM (Block Element Modifier) : Block(전체 감싸는 블록), Element(내부 요소), Modifier(기능/수정)으로 나누어 정의
#### OOCSS (Object Oriented CSS) : 객체 지향 CSS - 구조(w,h,border,pd,mg...)/외형(color,bg-color...) 분리, 컨테이너/내용 분리

___

### 1. SMACSS (Scalable and Modular Architecture for CSS)
- 장점 : 클래스명으로 예측, 재사용이 가능하며 확장이 용이함
- 단점 : 카테고리가 불분명할 수 있음, 코드를 나누어 작성하는 번거로움

- base : reset 같은 것을 포함, !important 사용 안함
```html
 body, form, p, table, button, fieldset, input ... {
      margin: 0;
      padding: 0;
  }
```
- layout : id 와 class 구분 뒤 l- 이라는 접두사 사용(layout > l-)
```html
.l-fixed #header {
    width: 650px;
}
```

- module : 스타일 재사용 많은 구성 요소(네비게이션바, 말풍선, 대화상자 등), .box>span 처럼 child 셀렉터 사용
- state : 접두사 is-,s-를 사용(.is-error, .is-hidden ...)
- theme : 사용자가 스타일을 재선언하며 사용, theme- 접두사 사용




### 2. BEM (Block Element Modifier) : block__element--modifier
- 장점 : 클래스명을 통해 직관적으로 구조 파악이 쉬움
- 단점 : 코드가 길어지고 복잡해짐, 기존 마크업에 기능 변경이 생기면 클래스명 재수정이 불편함

- block : 목적(menu,btn)에 맞게 설정, 환경(여백이나 위치)에 영향 받지 않음, 중첩 작성 가능
- element : block 안에서 특정 기능 수행(item, text, title)
- modifiers : 모양 상태를 정의함(color, size, disabled...)

### 3. OOCSS (Object Oriented CSS)
- 장점 : 공통 부분이 정의되어서 재사용됨, 동일한 클래스면 동일한 스타일임
- 단점 : 공통된 클래스가 많아 멀티클래스 사용, 유지보수 어려움, 가독성 떨어짐


<컨테이너와 콘텐츠 분리 예시>
```html
<div class="header common-width">Header</div>
<div class="footer common-width">Footer</div>

.header {
    position: fixed;
    top: 0;
}
.footer {
    position: relative;
    bottom: 0;
}
.common-width {
    width: 800px;
    margin: 0;
}
```

<구조와 외형 분리 예시>
```html
  // 기존 방식
  <a class=”instagram_btn instagram_skin”>Instagram</a>
  <a class=”facebook_btn facebook_skin”>Facebook</a>
 

  // OOCSS 적용
  <a class=”btn skin instagram”>Instagram</a>
  <a class=”btn skin facebook”>Facebook</a>

  .btn -> 공통 버튼 스타일 정의
  .skin -> 공통 스킨 스타일 정의
```
