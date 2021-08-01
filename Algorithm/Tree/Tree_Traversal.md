# 트리의 순회

*참고 블로그*

> [챕터7-2. 트리 | 순회방법(전위, 중위, 후위)](https://ldgeao99.tistory.com/402)

## 서론

트리도 그래프와 마찬가지로 dfs, bfs 탐색이 가능하다. 

그런데 이진 트리에서만 가능한 3가지의 순회 방법이 더 있다.

이 순회 방법은 재귀를 이용한다.

### 전위순회 (Pre-order)

> 루트 → 왼쪽 → 오른쪽

재귀를 이용하여 루트의 왼쪽 자식 노드를 루트로 하는 서브 트리를 프리오더 방식으로 순회하고, 오른쪽도 마찬가지로 순회한다.

- 루트를 가장 먼저 방문한다.
- DFS와 순서가 같다.

### 중위순회 (In-order)

> 왼쪽 → 루트 → 오른쪽

- 루트를 중간에 순회한다.

### 후위순회 (Post-order)

> 왼쪽 → 오른쪽 → 루트

- 루트를 가장 마지막에 순회한다.

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8b97a22a-5419-428a-beb5-5409ebc2fa23/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8b97a22a-5419-428a-beb5-5409ebc2fa23/Untitled.png)

- 전위 순회: A → B → D → E → C→ F → G
- 중위 순회: D → B → E → A → F→ C → G
- 후위 순회: D → E → B → F→ G → C → A

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fed1b6fd-7a71-4eea-9253-a79a68c25b74/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fed1b6fd-7a71-4eea-9253-a79a68c25b74/Untitled.png)

- 전위 순회: A → B → D → E → G → C → F
- 중위 순회: D → B → G → E → A → C→ F
- 후위 순회: D → G → E → B → F →  C→ A