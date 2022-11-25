# HTTP와 HTTPS

## HTTP의 문제점
* 평문으로 통신하기 때문에 도청 가능
* 통시 상대르 확인하지 않기 때문에 위장 가능
* 완전성을 증명할 수 없기 때문에 변조 가능

### TCP/IP는 도청 가능
![image](https://user-images.githubusercontent.com/38755868/203889189-80aaea8a-151d-42b8-96c4-3e5d0063e490.png)

#### 보완 방법

1. SSL (Secure Sockets Layer) / TLS (Transport Layer Security)

![image](https://user-images.githubusercontent.com/38755868/203889803-e9e6e8b9-7c69-4d3b-a7b4-6d92a68012f0.png)


### 통신 상대를 확인하지 않기 때문에 위장이 가능

#### 보완 방법

SSL이 인증서 제공해주므로 제 3자가 확인한 서버

### 완전성을 증명할 수 없기 때문에 변조가 가능

HTTPS에는 암호화 과정이 있기때문에 변조 불가
