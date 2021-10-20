## Red-Black Tree

- 자가 균형 이진 탐색 트리
- 레드 블랙 트리를 만족하기 위한 조건
    1. Root Property: **루트 노드의 색은 검정**이다
    2. External Property: **모든 external node들은 검정**이다
    3. Internal Property: **빨간노드의 자식은 검정**이다
        
        → 빨간색 노드가 연속으로 나올 수 없다
        
    4. Depth Property: **모든 리프노드에서 Black Depth는 같다**
        
        → 리프노드에서 루트노드까지 가는 경로에서 만나는 블랙 노드의 개수는 같다
        
- 조건에 따르면 레드블랙트리의 높이는 logN에 바운드된다

<br>

## 빨간색 노드가 연속으로 나오는 경우

: 현재 insert 된 노드의 uncle node의 색에 따라 처리 방법이 다르다

** uncle node: 부모의 **형제 노드**

### Restructuring

: uncle node가 검정일 때

1. 현재 삽입된 노드와, 부모 노드, 부모의 부모 노드(Grand Parent)를 오름차순 정렬
2. 부모 노드를 중간 노드로 하여 트리 재구조화
3. 올라간 부모 노드를 검정으로 바꾸고 자식 노드를 빨강으로 바꾸기
- Restructuring을 하기 전과 후의 블랙 노드의 수는 같다
    
    ⇒ Depth Property 조건 만족
    
    ⇒ Restructuring은 다른 서브 트리에 영향을 끼치지 않는다
    
- 한 번의 처리로 double red 해결 가능
- 시간복잡도 O(logN)
    
    → Restructuring 자체의 시간 복잡도는 1이지만, 새로운 노드를 삽입하기 위한 시간 복잡도 존재
    

### Recoloring

: uncle node가 빨간색일 때

1. 현재 삽입된 노드의 부모와 uncle 노드를 검정으로 하고 부모의 부모 노드(Grand Parent)를 빨강으로 한다
2. Double Red가 발생하였다면 다시 처리
- 한 번에 안 끝날 수도 있다. 최악의 경우에는 root 노드까지 올라가며 Recoloring을 해야할 수 있다
- **모든 리프노드에 대해 Black Depth가 1증가하기 때문에 여전히 Depth Property 만족**
- 시간복잡도 O(logN)
    
    → Recoloring 자체의 시간 복잡도는 1이지만, 새로운 노드를 삽입하기 위한 시간 복잡도 존재

<br>

## 레드 블랙 트리의 높이

- Depth Property 조건에 의해 모든 리프 노드에서 루트까지의 검정 노드의 개수는 같다
- 트리에서 가장 짧은 Detph Property는 검정 노드로만 이루어져 있을 것이고
- 가장 긴 Depth Property는 `검정-빨강-검정-빨강 ... -검정`으로 이루어져 있을 것
- 즉, 최대로 높이차가 나더라도 2배이다
- 따라서 레드블랙트리의 높이는 **logN**에 바운드된다
