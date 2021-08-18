Arrays.sort 혹은 PriorityQueue는 기본이 **오름차순 정렬**이다.

내림차순 정렬로 변경하기 위해 `Collections.reverseOrder();`를 사용한다.

<br>

```java
Arrays.sort(arr, Collections.reverseOrder()); // 일반 배열 내림차순
Arrays.sort(persons, Collections.reverseOrder()); // 객체를 넣는 경우 내림차순
PriorityQueue<Integer> priorityQueue = new PriorityQueue<>(Collections.reverseOrder());
// 우선순위 큐 내림차순
```