# Arrow Function

### 기존의 방식
```javaScript
let func = function(arg1, arg2, ...argN) {
  return expression;
};
```

### 화살표 함수
```javaScript
let func = (arg1, arg2, ...argN) => expression
```

#### 구체적 예시
```javaScript
let sum = (a, b) => a + b;

/* 위 화살표 함수는 아래 함수의 축약 버전 */

let sum = function(a, b) {
  return a + b;
};
```

### 화살표 함수의 다양한 경우
- 인수가 하나밖에 없다면 인수를 감싸는 괄호를 생략할 수 있다
```javaScript
let double = n => n * 2;
// let double = function(n) { return n * 2 }과 거의 동일
```
- 인수가 하나도 없을 땐 괄호를 비워둔다.(괄호 생략 불가)
```javaScript
let sayHi = () => alert("안녕하세요!");

```
