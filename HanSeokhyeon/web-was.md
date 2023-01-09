# Web과 Was 차이

먼가 맨날 애매하게 알고 있는거 같아서 다시 정리..

## 다양한 구조
* Client -> Web Server -> DB
* Client -> WAS -> DB
* Client -> Web Server -> WAS -> DB (우리팀 시스템 구조)

![image](https://user-images.githubusercontent.com/38755868/211232581-86fc1872-9c88-4fbe-9341-9149fd1836fa.png)

## Web Server

정적인 파일들을 제공하기 위한 서버
* html
* css
* js
* image
* ...

유명한 web server
* Apache Web server (우리회사에서 그동안 쓰는거)
* Nginx (앞으로 쓸거)
* 너는 머쓰니..?

## Was Server

* 과거에는 동적으로 html을 제작해서 제공
  * 마이페이지에 닉네임을 한석현 or 김민준으로 채워서 html 제작
* 현재는 API 서버로 만들고 json 통신
* Request -> WAS(DB조회, html 제작) -> Response(html)
* Request -> WAS(DB조회) -> Response(json) -> html 제작(js)

유명한 was server
* Spring(우리회사)
* node.js(너가 쓰는거)
* django
