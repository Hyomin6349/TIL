## 큐(Queue)

- 선형 자료구조
- FIFO(First In First Out): 선입 선출
- 데이터의 삽입이 이루어지는 곳을 꼬리(Rear)
- 데이터가 삭제되는 곳을 머리(Front)
- 데이터 삽입 enQueue, 데이터 삭제 deQueue

## java.util.Queue

: 큐에 필요한 연산을 선언해 놓은 **인터페이스**

⇒ LinkedList 클래스를 Queue 인터페이스의 구현체로 많이 사용

- offer(), poll(), isEmpty(), size()
- peek(): stack과 다르게 큐가 비어있어도 에러가 나지 않는다.

## 활용

**버퍼** 

: 데이터를 한 곳에서 다른 한 곳으로 전송하는 동안 일시적으로 그 데이터를 보관하는 메모리의 영역