# 동기 (Synchronous) vs 비동기 (Asynchronous)
<img src='https://velog.velcdn.com/images/daybreak/post/b7589efe-2188-4fc4-91ba-943a11d8f93a/%E1%84%83%E1%85%A9%E1%86%BC%E1%84%80%E1%85%B5%20%E1%84%87%E1%85%B5%E1%84%83%E1%85%A9%E1%86%BC%E1%84%80%E1%85%B5.jpg' width='50%' />
<br />

### 동기 : 요청과 그 결과가 동시에 일어난다(결과가 주어질 때까지 대기)
<br />
<img src='https://velog.velcdn.com/images%2Fguswns3371%2Fpost%2F1e696752-5f8c-43b2-8cf4-4cc513762189%2Fimage.png' width='50%' />
A가 끝나는 시간과 B가 시작하는 시간을 맞추면 Synchronous (동기)이다.<br />
ex) 자바의 synchronized 와 BlockingQueue가 있다.
<br />

<img src='https://velog.velcdn.com/images%2Fguswns3371%2Fpost%2Fb50808ff-b090-4396-a3fd-4e284908fdde%2Fimage.png' width='50%' />
A와 B가 시작 시간 또는 종료 시간이 일치하면 Synchronous (동기)이다.<br />
ex) A, B 스레드가 동시에 작업을 시작하는 경우 (자바의 CyclicBarrier), 메소드 리턴 시점 (A)과 결과를 전달받는 시점(B)이 일치하는 경우
<br />


### 비동기 : 요청과 결과가 동시에 일어나지 않는다(결과가 주어지는데 시간이 걸려도 그 동안 다른 작업이 가능)
<img src='https://velog.velcdn.com/images%2Fguswns3371%2Fpost%2F8d93245e-e316-4502-9774-ccae1b752636%2Fimage.png' width='50%' />
비동기는 작업을 수행하는 주체의 시작시간과 끝나는 시간에 관계없이 각자 별도의 시작 시간, 끝나는 시간을 갖는다

=> 작업을 수행하는 주체에 관점을 둔다

여기서 동시에라는 말은 실행되었을 때 값이 반환되기 전까지는 Blocking 되어 있다는 것을 의미한다.

## Blocking vs Non-Blocking
=> 제어권이 어디에 있느냐에 대한 관점
- Blocking : 직접 제어할 수 없는 대상의 작업이 끝날 때까지 제어권을 넘겨주지 않는 것이다.(호출하는 함수가 I/O 작업을 요청할 때 I/O 처리가 완료될 때까지 아무 일도 하지 못하고 기다리는 것)
<img src='https://velog.velcdn.com/images%2Fguswns3371%2Fpost%2Ff87c23bc-2194-4245-8212-6879b975bb2f%2Fimage.png' width='50%' />

- Non-Blocking : 직접 제어할 수 없는 대상의 작업처리 여부와 상관없다.(호출하는 함수가 I/O 작업을 요청한 뒤 I/O 작업에 대한 처리 완료 여부와 상관없이 바로 자신의 작업을 수행할 수 있는 것)
<img src='https://velog.velcdn.com/images%2Fguswns3371%2Fpost%2F1ad8b445-869d-49d9-925f-5ef7dd9cff28%2Fimage.png' width='50%' />

## Synchronous, Blocking 정리
- Blocking은 작업이 끝나기를 기다리다가 끝나면 다음 작업을 수행하는 것이고
- Synchronous는 두가지 이상의 대상이 서로 시간을 맞춰 행동하는 것이다.(시작 시간과 끝나는 시간을 같이 맞추거나, A가 끝나는 시간과 B가 시작하는 시간을 맞추는 것이다)

## Asynchronous, Non-Blocking 정리
- Asynchronous는 단지 두가지 이상의 대상이 서로 시간을 맞춰 행동하지 않는 것
- Non-Blocking은 다른 작업이 끝날 떄까지 기다리지 않는 것
