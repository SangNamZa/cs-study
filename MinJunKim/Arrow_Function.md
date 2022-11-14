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

/* 위 화살표 함수는 아래 함수의 축약 버전

let sum = function(a, b) {
  return a + b;
};
*/
```
