# Array vs Linked List

![image](https://user-images.githubusercontent.com/38755868/189009113-cedfaa9c-90c4-4d5a-afd3-3860a9c80f8f.png)

## Array

* 논리적 저장 순서와 물리저 저장 순서가 일치한다.
* 접근
  * Index로 해당 element에 접근이 가능하다.
    * Time complexity : Big-O(1)
* 삽입 & 삭제
  * 빈 공간을 채워줘야 하므로 shift하는 비용이 발생한다.
    * Time complexity : Big-O(n)
    * ![image](https://user-images.githubusercontent.com/38755868/189010061-9dcbfc51-b7b0-477e-b22b-2d90ab01d89c.png)

## Linked List

* 각각의 element들은 자기 자신 다음에 어떤 element인지만을 기억
* 접근
  * 해당 element를 찾기 위해 첫번째 element부터 확인해야한다.
    * Time complexity : Big-O(n)
* 삽입 & 삭제
  * 다음 element 정보만 수정하면 된다.
    * Time complexity : Big-O(1)
    * ![image](https://user-images.githubusercontent.com/38755868/189011768-9de12715-0bef-47e7-905d-e3c7009b349e.png)
  * 다만 해당 element를 찾는 과정을 먼저 요구하므로
    * Time complexity : Big-O(n) + Big-O(1) = Big-O(n)
* 접근, 삽입, 삭제 모두 array에 비해 이득이 없어 보이지만 꼭 필요한 곳이 있는 자료구조이다.
  * Queue
    * ![image](https://user-images.githubusercontent.com/38755868/189012104-4c0f0385-b66f-4616-b7ac-707a0bccc2f2.png)

