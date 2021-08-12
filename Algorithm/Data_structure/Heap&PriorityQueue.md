## Heap

: **완전 이진 트리**에 있는 노드 중에서 키 값이 가장 큰 노드나 키 값이 가장 작은 노드를 찾기 위해서 만든 자료구조

- 최대 힙(max heap): 키 값이 가장 큰 노드를 찾기 위한 완전 이진 트리
    - 부모 노드의 값 > 자식 노드의 값
    - 루트 노드: 키 값이 가장 큰 노드
    - 새로운 노드에 대해 $logN$만 비교하면 가장 큰 값인지 알 수 있다
- 최소 힙(min heap): 키 값이 가장 작은 노드를 찾기 위한 완전 이진 트리
    - 부모 노드의 값 < 자식 노드의 키 값
    - 루트 노드: 키 값이 가장 작은 노드
    - 최대 힙과 마찬가지로 $logN$만 비교하면 가장 작은 값인지 알 수 있다.## Heap의 삽입 연산

- 최대 힙 혹은 최소 힙을 만족하는지 leaf 노드에서 root노드까지 비교해간다
- $logN$만 비교
- 10억개의 노드가 있는 힙에서 삽입 연산은 30번만 비교하면 된다.

<br>

## Heap의 삭제 연산

- **루트 노드의 값만 삭제**할 수 있다
- 삭제하는 값은 힙에서 가장 작거나 가장 큰 값
- 루트 노드를 두 자식과 비교해가며 **더 큰 자식값**과 자리를 바꾼다
- 루트 노드가 말단까지 왔을 때 제거 → 힙의 구조를 해치지 않도록
- $logN$의 시간 복잡도

<br>

---

<br>

## PriorityQueue

- 우선순위 정보를 같이 저장하는 큐
- FIFO 순서가 아니라 **우선순위**에 따라 poll() 연산이 일어난다.

<br>

## java.util.PriorityQueue

- **최소 힙**으로 Heap을 유지 (natural Ordering)
- 큐를 구성하는 원소는 비교 가능해야 함 ⇒ **Comparable** 인터페이스를 구현해야 함

<br>

### Comparable

- int compareTo() 메서드를 오버라이드
- **자신과 상대**를 비교 → 인자 한 개 필요
- `return this - target` : 오름차순


### Comparator

- int comapare() 메서드를 오버라이드
- **원소 두 개**를 비교 → 인자 두 개 필요
- `return o1 - o2` : 오름차순