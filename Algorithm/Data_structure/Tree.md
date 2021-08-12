## 트리

- 비선형 구조 → 선후관계가 1대1이 아님
- 원소들 간에 1:n 관계를 가짐
- 원소 간의 계층 관계가 존재

<br>

## 노드

- 트리의 원소
- 최상위 노드를 root 라고 한다 → 트리 전체를 탐색할 수 있는 출발지
- 단말 노드(left node): 트리의 끝 노드
- 형제 노드: 부모 노드가 같은 자식 노드 간의 관계
- 조상 노드: 간선을 따라 루트 노드까지 이르는 경로에 있는 모든 노드들
- 자손 노드: 서브 트리에 있는 하위 레벨의 노드들

** 서브 트리: 부모 노드와 이어진 간선을 끊었을 때 생기는 트리

<br>

## 간선

- 노드와 노드를 연결하는 선으로 부모 노드와 자식 노드를 연결
- 상위 노드와 하위 노드를 연결한다

<br>

## 차수

- 노드에 연결된 자식 노드의 수
- 트리의 차수: 트리에 있는 노드의 차수 중에서 가장 큰 값

<br>

## 높이

- 노드의 높이: 루트에서 노드에 이르는 간선의 수
- 트리의 높이: 트리에 있는 노드의 높이 중에서 가장 큰 값

<br>

## 이진 트리

- 차수가 2인 **트리**
- 각 노드가 자식 노드를 최대한 2개 까지만 가질 수 있는 트리
- 자식 노드의 개수는 2개 이하 → 구현의 단순화, 탐색의 편의성이 높아짐
- 왼쪽 자식 노드와 오른쪽 자식 노드
- 높이 i에서의 노드의 최대 개수는 $2^i$개
- **포화 이진 트리**: 모든 레벨에 노드가 포화 상태로 차 있는 이진 트리

    ⇒ 높이가 h일 때, 최대의 노드 개수인 2^(h+1)-1 개를 가진다

- **완전 이진 트리**: 1~n번 노드까지 루트에서 부터 이진 트리를 만족시키며 채워진 트리

    ⇒ 배열로 표현하기 쉬움: 루트를 1이라 할때, 왼쪽 자식은 부모 노드 번호의 $*2$, 오른쪽 자식은 부모 노드 번호의 $*2+1$과 같다