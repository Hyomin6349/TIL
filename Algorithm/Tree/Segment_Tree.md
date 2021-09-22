
## Segment Tree

: 배열의 구간 합을 트리형태로 저장하여 **배열의 특정 원소 값의 변경 후 구간 합을 구하는** 과정의 시간 복잡도를 개선한 트리

<br>

## 만들기

- 노드의 개수: 리프 노드가 배열의 수와 같기 때문에 전체 트리의 노드의 수는 2^(logN+1) -1
- 재귀적으로 트리를 생성한다

    ```java
    long init(long [] a, long [] tree, int node, int start, int end) {
        if (start == end) {
            return tree[node] = a[start];
        } else {
    				int mid = (start+end)/2;
            return tree[node] = init(a, tree, node*2, start, mid) + init(a, tree, node*2+1, mid+1, end);
        }
    }
    ```

    - start와 end가 같으면 리프 노드 ⇒ 배열 값 넣어주기
    - 오른쪽 자식과 왼쪽 자식을 합한 것을 현재 노드에 대입하기

<br>

## 합 찾기

합을 찾아야하는 구간 left와 right가 주어졌을 때, 루트부터 트리를 순회하며 노드가 담당하는 start, end와 비교하며 합을 찾아준다. 

다음과 같은 4가지 경우가 존재

1. left, right와 start, end가 겹치지 않는 경우 (`left>end || right<start`) → 찾는 부분이 아님 ⇒ `return 0`
2. left, right가 start, end를 완전히 포함하는 경우 (`left<=start && end<=right`) → 찾는 부분과 일치 ⇒ `return tree[node]`
3. start, end가 left, right를 완전히 포함하는 경우 (start≤left && right≤end)→ 자식 노드로 더 들어가야 함 → 오른쪽 왼쪽 자식으로 탐색
4. 1,2,3을 제외한, left, right와 start, end가 겹쳐져 있는 경우 → 오른쪽 왼쪽 자식으로 탐색

```java
long sum(long[] tree, int node, int start, int end, int left, int right) {
    if (left > end || right < start) { //1번 경우
        return 0;
    }
    if (left <= start && end <= right) {
        return tree[node];
    }
    return sum(tree, node*2, start, (start+end)/2, left, right) + sum(tree, node*2+1, (start+end)/2+1, end, left, right);
}
```

<br>

## 수 변경하기

리프 노드를 변경, 리프노드에 도달하기 까지의 모든 노드를 변경해야 한다

- 원래 값과 변경 값의 차이를 더해준다: arr[i] += val - arr[i]

```java
void update(long[] tree, int node, int start, int end, int index, long diff) {
    if (index < start || index > end) return;
    tree[node] = tree[node] + diff;
    if (start != end) {
        update(tree,node*2, start, (start+end)/2, index, diff);
        update(tree,node*2+1, (start+end)/2+1, end, index, diff);
    }
}
```

- 인덱스가 구간에 포함되지 않으면 return
- 포함 된다면 차이를 더해준다
- 리프노드가 아니라면 왼쪽, 자식노드로 업데이트를 재귀적으로 수행

<br>

## 참고

[세그먼트 트리 (Segment Tree)](https://www.acmicpc.net/blog/view/9)