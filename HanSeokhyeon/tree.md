# Tree

코딩테스트보다 실무구조에서 많이 만나게 되는 자료구조

## 정의

트리 구조(tree 構造, 문화어: 나무구조)란 그래프의 일종으로, 한 노드에서 시작해서 다른 정점들을 순회하여 자기 자신에게 돌아오는 순환이 없는 연결 그래프이다.

### 그래프
![image](https://user-images.githubusercontent.com/38755868/191413493-589c2c45-8be2-48b0-b62f-e5ef7f2363ad.png)

그래프는 vertex와 edge로 구성된 한정된 자료구조를 의미한다. vertex는 정점, edge는 정점과 정점을 연결하는 간선이다.

![image](https://user-images.githubusercontent.com/38755868/191413896-b6badb03-c6f7-4d0d-8234-173763d2f557.png)


### 트리
![image](https://user-images.githubusercontent.com/38755868/191413551-018b86c2-3df5-4c68-9807-4013f65401e8.png)


## 구현
```javascript
class Node {
  constructor(data, left = null, right = null) {
    this.data = data;
    this.left = left;
    this.right = right;
  }
}
```

## 예시
* [네이버 쇼핑 카테고리](https://shopping.naver.com/home/p/index.naver)
* [디렉토리 구조](https://github.com/SangNamZa/algorithm-study)
* [블로그 LNB](https://hanseokhyeon.tistory.com/4#comment13859066)
* Git tree
  * ![image](https://user-images.githubusercontent.com/38755868/191419197-44a52402-f911-4e0e-b9b8-fb327736b138.png)
