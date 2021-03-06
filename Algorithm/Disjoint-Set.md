## Disjoint-set

: 서로소 또는 상호배타 집합들은 서로 **중복 포함된 원소가 없는** 집합들

⇒ 교집합이 없다

- 집합에 속한 **하나의 특정 멤버**를 통해 각 집합들을 구분
- 연결 리스트, 트리로 표현
- Make-set(x): 집합 만들기
- Union(x, y): x와 y집합 합치기
- Find-Set(x): x가 속한 집합의 대표 원소 찾기

<br>

## 서로소 집합 표현

### 연결리스트

- 같은 집합의 원소들은 하나의 **연결리스트**로 관리
- 연결리스트의 가장 앞 원소는 **대표 원소**
- 각 원소는 집합의 **대표 원소를 가리키는 링크**를 가짐

### 트리

- 같은 집합의 원소들은 하나의 **트리**로 관리
- 트리의 루트는 각 집합의 **대표 원소**

<br>

## Find-Set 연산 효율 높이기

: 원래 Find-Set 연산은 부모의 부모를 찾아가 root 까지 찾아야 함. 이 과정은 연산 효율이 좋지 않음!

### Rank(depth)를 이용한 Union

- 각 노드는 자신을 루트로 하는 subtree의 높이를 Rank라는 이름으로 저장한다.
- 두 집합을 합칠 때 rank가 낮은 집합을 rank가 높은 집합에 붙인다. ⇒ Rank의 변화가 없음
- 두 집합의 rank가 같으면 어느 쪽에 붙이든 rank가 1 증가한다.

### Path compression

- Find-Set을 행하는 과정에서 만나는 모든 노드들이 직접 **root를 가리키도록** 포인터를 바꾸어 준다.
- rank가 큰 트리에서 rank가 작은 트리로 압축