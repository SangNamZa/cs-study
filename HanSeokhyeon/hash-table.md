# Hash table

[이글짱이군](https://baeharam.netlify.app/posts/data%20structure/hash-table)

## 해싱(Hashing)

임의의 길이의 값을 해시함수(Hash Function)를 사용하여 고정된 크기의 값으로 변환하는 작업을 말한다.

![image](https://user-images.githubusercontent.com/38755868/199865021-4c380f76-50af-4a29-b9ac-82dd9437ade5.png)

* dog -> hash algorithm -> 142(인덱스)
* 해싱을 사용하여 데이터를 저장하는 자료구조를 해시 테이블(Hash Table)이라고 하며 이는 기존 자료구조인 이진탐색트리나 배열에 비해서 굉장히 빠른 속도로 탐색, 삽입, 삭제를 할 수 있기 때문에 컴퓨터 공학도라면 반드시 알아야 한다.

## 해시 테이블

* 해시함수를 사용하여 변환한 값을 색인(index)으로 삼아 키(key)와 데이터(value)를 저장하는 자료구조
* 기본연산으로는 탐색(Search), 삽입(Insert), 삭제(Delete)

### Direct Address Table

* 가장 간단하 형태의 해시테이블
* 키 값을 주소로 사용하는 테이블
* 키 값이 100이며 배열 인덱스 100에 저장

![image](https://user-images.githubusercontent.com/38755868/199865643-d3c26c8b-6be5-4d20-9954-c2b3e7ff33e0.png)

* 탐색,삽입,삭제 연산을 모두 O(1) 에 할 수 있지만 다음과 같은 한계점이 있다.
  * 최대 키 값에 대해 알고 있어야 한다.
  * 최대 키 값이 작을 때 실용적으로 사용할 수 있다
  * 키 값들이 골고루 분포되어있지 않다면 메모리 낭비가 심할 수밖에 없다.

### Hash Table

![image](https://user-images.githubusercontent.com/38755868/199865810-9addcb3e-357c-46b8-9efb-4ee4294614b0.png)

* 해시함수를 사용하여 특정 해시값을 알아내고 그 해시값으 인덱스로 변환하여 키 값과 데이터를 저장하는 자료구조
* 충돌(Collision)이라는 문제가 발생

#### 적재율
* K : 키의 개수
* N : 해시 테이블의 크기
* 적재율 : K / N
* Direct Address Table은 키 값을 인덱슬 사용하는 구조이기 때문에 적재율이 1이하이며 적재율이 1 초과인 해시 테이블의 경우느 반드시 충돌
  * 길이가 100인 배열인데 키의 개수가 101개면 충돌
  * K : 101
  * N : 100
  * 적재율 : 101/100 > 1
