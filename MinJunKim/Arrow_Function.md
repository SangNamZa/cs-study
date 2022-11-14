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

### 화살표 함수의 특징
#### 매개변수 지정 방법
- 매개변수가 하나도 없을 땐 괄호를 비워둔다.(괄호 생략 불가)
```javaScript
let sayHi = () => alert("안녕하세요!");
```
- 매개변수가 하나밖에 없다면 인수를 감싸는 괄호를 생략할 수 있다
```javaScript
let double = n => n * 2;
// let double = function(n) { return n * 2 }과 거의 동일
```
- 매개변수가 여러 개인 경우, 소괄호를 생략할 수 없다
```javaScript
(x, y) => { ... } 
```


- 본문이 여러 줄이면 중괄호를 사용해야함.(return 지시자로 결과값을 반환해야함)
```javaScript
let sum = (a, b) => {  // 여러 줄이면 중괄호 사용
  let result = a + b;
  return result; // 중괄호를 사용했다면, return 지시자로 결괏값을 반환
};

alert( sum(1, 2) ); // 3```


- 동적인 함수로 사용 가능
```javaScript
let age = prompt("나이를 알려주세요.", 18);

let welcome = (age < 18) ?
  () => alert('안녕') :
  () => alert("안녕하세요!");

welcome();
```

- 객체 반환시 소괄호를 사용
```javaScript
() => { return { a: 1 }; }
() => ({ a: 1 })  // 위 표현과 동일
```

#### 화살표 함수는 익명 함수로만 사용 가능
```javaScript
const pow = x => x * x;
console.log(pow(10)); // 100
```

#### 화살표 함수는 콜백 함수로 사용 가능
```javaScript
const arr = [1, 2, 3];
const pow = arr.map(x => x * x);

console.log(pow); // [ 1, 4, 9 ]
```
