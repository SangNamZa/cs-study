# 스레드란?
프로세스가 할당받은 자원을 이용하는 실행의 단위(작업을 담당하는 최소 실행 단위)
<img src='https://velog.velcdn.com/images%2Fgil0127%2Fpost%2F90c4513d-14c6-476b-8eb6-452f7f0fb107%2F7.PNG' width='50%' />
<img src='https://images.velog.io/images/gil0127/post/540376e9-9eb4-46d8-9cff-816a1d9cce1f/싱글%20vs%20멀티.png' width='50%' />

## 싱글스레드
- 하나의 프로세스에서 하나의 스레드로만 실행된다
- 여러 개의 CPU르 사용하지 못 하고, 하나의 작업이 완료되어야 다음 작업이 이루어진다
- heap, code, data와 같은 자원들의 동기화의 영향이 적다
- CPU만 사용하는 간단한 작업의 경우 개발이 더 쉽고 멀티스레드보다 실행이 빠르다

## 멀티스레드
- 하나의 프로세스에서 2개 이상의 스레드가 병행적으로 실행된다
- context switching이 이루어져 각각의 스레드가 부분적으로 이루어진다(스위칭이 매우 빨라서 동시에 진행하듯이 느껴질뿐 동시 작업으 아니다)
- heap, code, data의 공유가 이루어지기에 동기화가 중요하며, 안그럴 경우 다르 결과값이 나온다
- 개발 난이도가 높으며 스레드 수만큼 자원 이용이 많다
- 프로세스의 context switching과 달리 스레드 간의 context switching은 캐시 메모리를 비울 필요가 없기 때문에 더 빠르고 경제적이다
- context switching, 자원의 동기화 작업으로 인하여 싱글스레드에 비해서 느리다

## 멀티프로세스 vs 멀티스레드
<img src='https://t1.daumcdn.net/cfile/tistory/230A334B5822F74D08' width='50%' />
<img src='https://t1.daumcdn.net/cfile/tistory/217D00505822F78905' width='50%' />
멀티프로세스는 자신만의 메모리 영역이 유지되는 반면, 멀티스레드에서는 자원들이 동기화가 이루어져야한다
