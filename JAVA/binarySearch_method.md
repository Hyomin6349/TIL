## Arrays.binarySearch

: Arrays의 클래스에 존재하는 이진탐색 메서드를 살펴보자

- `Arrays.binarySearch(int[] arr, key)`
- `Arrays.binarySearch(int[] arr, int from, int to, key)`
    - 구간에서 key 값을 찾을 때
    - from부터 to-1 까지를 탐색
- key가 arr에 존재하는 경우 → index를 반환
- key가 arr에 존재하지 않는 경우 → `-(insert point) -1` 을 반환