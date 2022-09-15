# Stack and Queue

코딩테스트에도 자주 나오고 실무에서도 자주 나오는 자료구조(필수!!)

## Stack

### 특징
![image](https://user-images.githubusercontent.com/38755868/190305683-cfa6cd3a-ab98-482d-81e5-1caebe30157d.png)

* Stack의 사전적 의미 - 쌓다
* 아래부터 차곡차곡 위로 쌓아가는 구조
* FILO (First In Last Out, 선입후출)
* LIFO (Last In First Out, 후입선출)

### 예시
* 하노이탑
  * ![image](https://user-images.githubusercontent.com/38755868/190302871-e9cb08c5-f34b-4b60-9384-f791a81727f3.png)
  * 가장 나중에 쌓은 고리가 가장 먼저 꺼내진다.
* 책자 가져가기
  * ![image](https://user-images.githubusercontent.com/38755868/190305346-014c5926-6d45-4dc5-b93c-8758a4e259f8.png)
 
### 구현
![image](https://user-images.githubusercontent.com/38755868/190305683-cfa6cd3a-ab98-482d-81e5-1caebe30157d.png)

#### Array
* ![image](https://user-images.githubusercontent.com/38755868/190307255-35692db6-29c0-481f-b150-daf270f1a7d7.png)
  * arr.push(1)
  * arr.push(2)
  * arr.push(3)
  * arr.pop()
  * arr.pop()
  * arr.pop()
* 삽입
  * O(1)
* 삭제
  * O(1)  

## Queue
![image](https://user-images.githubusercontent.com/38755868/190305783-4ccd9b2e-096d-4240-b0c8-12727bb4af29.png)

* Queue의 사전적 의미 - 차례를 기다리는 사람이나 승용차의 열
* 데이터를 줄세우는 구조
* FIFO (First In First Out, 선입선출)
* LILO (Last In Last Out, 후입후출)

### 예시
* 영화관, 은행, 놀이공원 등등 줄서기
  * ![image](https://user-images.githubusercontent.com/38755868/190306273-29809c01-09ba-4eba-9e4d-9059601771da.png)
* 예매 시스템
  * ![image](https://user-images.githubusercontent.com/38755868/190306512-60fdff6c-6e1e-4afe-9e52-75d57642024f.png)

### 구현
![image](https://user-images.githubusercontent.com/38755868/190305783-4ccd9b2e-096d-4240-b0c8-12727bb4af29.png)

#### Array
* ![image](https://user-images.githubusercontent.com/38755868/190307255-35692db6-29c0-481f-b150-daf270f1a7d7.png)
  * arr.push(1)
  * arr.push(2)
  * arr.push(3)
  * arr.pop(0)
  * arr.pop(0)
  * arr.pop(0)
* 삽입
  * O(1)
* 삭제
  * O(n) <- 비효율적

#### Linked List
* ![image](https://user-images.githubusercontent.com/38755868/190307127-5ef857dc-739e-4a68-b62c-dcf5a7836e40.png)
  * arr.push(1)
  * arr.push(2)
  * arr.push(3)
  * arr.pop()
  * arr.pop()
  * arr.pop()
* 삽입
  * O(1)
* 삭제
  * O(1)
