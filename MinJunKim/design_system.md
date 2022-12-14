# 디자인 시스템

### 디자인 시스템의 구성요소
- 비주얼 언어
    - 컬러 토큰 ex) Red100, Red200…
    - 그 외 : 타이포그래피 토큰, 사이즈 토큰, 여백 토큰, 트랜지션 토큰 등등
- 컴포넌트
    - 토큰 단계 다음으로 만든다
    - 앞서 만든 토큰을 가지고 컴포넌트의 생김새나 동작을 만든다
    - ex)
    - ![Losding](https://user-images.githubusercontent.com/101058125/195037290-943ba818-0018-4b29-9881-cf99e9885daa.png)
    - 컴포넌트 옵션의 제약으로 일관성과 재사용성 획득
    
- 패턴
	- 컴포넌트 다음 단계
	- 컴포넌트 옵션으로 생김새를 제약한다면 패턴에서는 사용처를 제약한다
	- ex) blue button : 한 화면에 하나만 사용, CTA 역할을 하는 버튼에 사용 / red button : 한 화면에 하나만 사용, 되돌릴 수 없는 작업의 경우에 경고 용도로 사용

![스크린샷 2022-10-11 오후 4 13 19](https://user-images.githubusercontent.com/101058125/195037887-8b1d88b4-7168-403f-8582-4b51a259ee79.png)

코드를 재사용하고, 디자인에 일관성이 생기게되었다 (이전에는 버튼 하나 조차도 다시 만들고, 그게 미세하게 달랐다)

<br />
<br />

### 디자인 시스템을 만들고 나서 생기는 문제들
1. 코드를 디자인에 일치시키는 어려움 - 컴포넌트 스택 가이드가 있지만, 디자이너와 개발자가 각자 컴포넌트를 구현하다 보니 세세한 구현이 달랐다. ex)
![스크린샷 2022-10-11 오후 4 18 18](https://user-images.githubusercontent.com/101058125/195038095-9f01e014-6fad-49c5-8473-4844f8e058f4.png)
![스크린샷 2022-10-11 오후 4 19 32](https://user-images.githubusercontent.com/101058125/195038105-7849da19-ddc6-4e04-8b59-d0b15cc0bec2.png) <br />
-> 디자인 툴에서는 동적인 구현이 불가했기에, 코드가 작성되고 배포된 후에 디자이너가 발견하기도 한다.   

2. 디자이너와 개발자가 서로 다른 언어를 원한다.(비주얼 중심의 디자이너 언어 !== 기능 중심의 개발자 언어 : red vs danger)   
3. 엄격함과 유연함 사이의 어려움 : 효율성, 일관성 vs 디자인 자유도 사이의 밸런스   
<br />
<br />

### 디자인 시스템 넘어서
#### 디자인 시스템 가이드가 있어도 있던 한계
디자인 시스템 가이드가 스펙 문서로 남아있었다.<br />
디자이너 : 디자인 시스템 가이드 -> 디자인(스케치 컴포넌트 라이브러리) : 버튼 선택 - 버튼색상 선택 - variation 선택 -> 디자인 시안<br />
개발자 : 디자인 시스템 가이드 -> 개발(React 라이브러리) 컴포넌트를 만든다(스토리북) -> 구현 결과물<br />
<br /><br />
이 과정은 문서를 통해서 사람이 구현한다(human error), 디자인 툴에서는 코드처럼 다양한 구현이 어렵다.<br />
디자인과 코드 사이에 강한 의존 관계를 만들어야했다.<br />
<br />
<br />
디자인 툴에서도 코드를 사용할 수 있으면 좋을텐데 라는 수요에 프레이머를 찾게됨
![Code Component](https://user-images.githubusercontent.com/101058125/195038369-71fa6afc-9ec1-477c-934a-b116fa34ca4d.png)

#### 디자인과 코드의 동기화
디자인 시안에서부터 반응형과 같은 특성들이 보여지고, 버튼, 타이핑 등등도 완성된 리액트 앱처럼 작동함.<br />
디자인 시스템 가이드 -> 개발(React 라이브러리) : 구현 결과물 ->디자인(Code Component) : 디자인 시안<br />
리액트 컴포넌트를 수정하면 디자인 컴포넌트도 수정됨 : 코드 동기화가 실현됨<br />
<br />

#### 동기화가 되었지만 적용이 선택적으로 이루어짐
기존에는 디자인 시안을 개발자가 보기 슆게 hand-off 기능을 사용하였음(제플린) : 위치나 크기값 등을 알아내는 과정<br />
어디까지가 디자인 시스템 컴포넌트인지, 디자이너의 커스터마니즈 디자인인지 파악하기 어려웠음<br />
디자인 시안의 레이어의 이름을 통해서 컴포넌트 속성을 유추하는 방식으로 일했었음<br />
이럴 경우 모든거 하나하나 다 클릭하면서 알아봐야함<br />
디자인시스템에 익숙하지 않은 신규 입사자들의 러닝커브가 점점 높아졌음.<br />
프레이머에서 구현한 디자인은 이미 리액트 앱인데, 이것을 다시 클릭해서 알아보면서 개발하는게 이상했음<br />
<br />
디자인 시스템을 표현하는 새로운 핸드오프 도구를 만들기로함<br />
요소 선택하면 디자인 시스템이라는 것을 명시적으로 표현해야했음(이 다음 과정은 요약…)<br />
<br />
<br />


### 그 다음 단계 = Design Syntax Tree (DST)

![DST Element](https://user-images.githubusercontent.com/101058125/195038441-2db26281-db4f-4518-b9cd-0fcdc5b8d25a.png)
![Structured Design](https://user-images.githubusercontent.com/101058125/195038461-1f8cbc25-406c-4c25-95f8-ad382db94846.png)<br />
컴포넌트가 이미 2만개가 될정도로 다양해도, 디자이너가 다 파악하기 어려워 그냥 커스터마이즈 하는 경우들이 많이 발생<br />
그래서 디자인 시스템 사용률을 높이는, 디자인 시스템 Coverage 계산기 확장자를 만들어냄<br />
디자인 툴에서 디자인 시스템을 벗어났다는 것을 알려줌(design linter)
![Coverage](https://user-images.githubusercontent.com/101058125/195038516-a9bb4390-8e43-4ed4-a26a-f4dae42f6577.png) <br />
디자인 시스템에서 적용하는 퍼센테지를 높이면서 디자인하게 됨.<br />
더 다양한 디자인을 담아내고자 함 (3d, animation 등등)



