CSS 트랜드 지표 링크 : https://2021.stateofcss.com/en-US/technologies
## Post-processors / CSS Framework / CSS-in-JS
### 1. Post-processors(전처리기)
<img src='https://miro.medium.com/max/1400/1*bdBOILv1QXL_lTUbW7d-sA.jpeg' width='50%' />
기존 CSS 씬택스보다 더 간편한 문법을 이용해서 개발하고, 사용자들에게 배포하기 전에는 순수 CSS로 변환된다.   
(변수 설정, 부모 선택자 안에 자식 선택자 중첩적으로 설정, 모듈 별로 나누기 등이 가능)   
Sass, PostCSS가 이에 해당, 요즘 대세

### 2. CSS Framework 의 대표적인 리스트(범위를 크게 잡았음)
- Bootstrap (사용도 1등)
- PostCSS (Post-processor)
- Tailwind CSS
- Material UI
- Styled-Components (CSS-in-JS)

### 3. CSS-in-JS
JS에서 CSS를 정의할 수 있다.
대부분의 라이브러리들이 전체적으로 사용도가 낮다. (2021년 전체 웹 사이트 중 3% 정도가 사용했다는 자료도 있다)
CSS-in-JS 중에서는 styled Components, emotion이 1,2등

### 특징 비교(Post-processors vs framework vs CSS-in-JS)
- PostCSS vs Styled-Components
  - 기존의 Css 파일에 정리하는 방식이냐 JS에 css를 정리하냐에 따른 호불호가 갈린다.   
  - JS에 css를 정리하면 동적으로 스타일링을 변경할 수 있어서 좋다 라고 생각하기도 하지만,    
  - 비지니스 로직에 들어있어야할 js 파일 안에 스타일링이 섞여있어서 presentation과 behavior이 섞여 있어서 지저분하고 유지보수가 힘들다고 느끼기도 한다.

- Bootstrap, Tailwind CSS, Material UI
  - 미리 만들어진 ui 컴포넌트를 가져다 쓰기에 빠른 개발이 가능해서 좋음

- 정형화된 스타일링이 싫어 직접 만들어 쓰는 경우 postcss, styled-components 를 사용하거나 tailwind에서 스타일링을 customization 해서 사용한다.

### 구체적 예시
#### Styled-Components
<img src='https://cdn-media-1.freecodecamp.org/images/1*DIFji4ZmJa4_H3EpbG2XAw.png' width='50%' />
컴포넌트 단위로 스타일링하기 때문에 개별 케이스로 분리해 css를 작성한다 <br />    
구체적 사용법 가이드 : https://nykim.work/107

#### Tailwind CSS
<img src='https://images.ctfassets.net/rpmifyuylbfw/1c2mvLaFJJjZVQ4GBu75Uj/26c7447710beb22673a6827d26509442/autocomplete.png' width='50%' />
className에 작성하기에 너무 길어지는 단점, 어느 부분인지 바로 체크 가능한 직관적임은 장점.   
유틸리티 클래스를 지원해주기에 간편하다.

#### Tailwind CSS & Styled-Components
<img src='https://velog.velcdn.com/images%2Fjinsunkimdev%2Fpost%2Fcdd7d961-0b40-4a47-a574-98638e92526a%2Fcarbon2.png' width='50%' />
<img src='https://velog.velcdn.com/images%2Fjinsunkimdev%2Fpost%2Fe2b2e324-c0b5-48a6-87e6-8508e2e27168%2Fcarbon%203.png' width='50%' />
<img src='https://images.velog.io/images/jinsunkimdev/post/49d33865-3d64-48b6-bf5c-a9f4736b5c60/carbon%204.png' width='50%' />
Tailwind 의 유틸리티 클래스와 Styled Components의 CSS-in-JS 의 도움으로 컴포넌트를 꺠끗하게 유지하는 방법도 있다.
