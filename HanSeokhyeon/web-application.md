# 현대적인 웹 애플리케이션의 구조

![image](https://user-images.githubusercontent.com/38755868/192913132-e8fa8a70-c1b6-49c0-97c8-57d79335298c.png)

## Client

* 고객들이 직접 사용하는 부분
* HTML, CSS, JS, Image 등을 받아 사용자가 사용할 수 있도록 렌더링해준다.
* Web browser (PC / Mobile)
    * Chrome
    * Safari
    * Samsung Internet
    * Internet Explorer
* App
    * Native App
    * Hybrid App
    * [비교](https://www.hanl.tech/blog/native-vs-hybrid-vs-pwa/)

## Web Server

* 고객들이 사용할 정적 리소스를 제공
* HTML, CSS, JS, Image 등
* Vue.js, React로 개발한 결과물을 빌드하여 web server에 배포
    * npm run build하고 나면 생기는 build 디렉토리
* Apache
* Nginx
* Node.js의 자체 웹서버를 그냥 사용하기도 하나 대규모 사이트에서는 별도 웹서버를 사용


## Application Server

* 우리회사에서는 WAS라고 부름. (Web Application Server)
* 백엔드 서버
* 비즈니스 로직을 담당
    * 주문, 결제, 취소, 환불, 상품추천 등등
* CRUD
    * Create - 데이터 저장
    * Read - DB에서 데이터를 꺼내와 적절히 가공후 제공
    * Update - 데이터 변경
    * Delete - 데이터 삭제
* Java Spring
* Node.js
* Django (python)
 

## Database

* 데이터를 저장하는 곳
* SQL
    * Oracle
    * MySQL
    * Postgresql
* NoSQL
    * mongoDB
    * Redis
    * Firebase
    * Elasticsearch
* [DB 순위](https://zetawiki.com/wiki/DB엔진_순위)
