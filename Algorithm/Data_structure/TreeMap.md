## TreeMap

- 이진 트리를 기반으로 한 Map 컬렉션
- TreeMap에 저장된 객체는 자동 오름차순 정렬된다
    - 숫자는 값으로, 문자열 타입은 유니코드로 정렬
    - 부모 키 값과 비교하여 키값이 낮은 것은 왼쪽, 높은 것은 오른쪽 정렬
- HashMap보다 추가, 삭제 연산이 오래 걸린다
- 정렬된 상태로 Map을 유지해야할 때, 범위 검색을 할때 많이 사용

### 전체 값 출력

- `keySet()` : 전체 key를 가져오는 경우
- `entrySet()` : 전체 key와 value를 가져오는 메서드
    
    ```java
    for (Entry<Integer, String> entry : map.entrySet()) {
        System.out.println("[Key]:" + entry.getKey() + " [Value]:" + entry.getValue());
    }
    ```
    
- keySet을 사용하는 경우 get(key) 연산을 같이 활용하는 경우가 많은데 get하는 곳에서 시간이 많이 소모되므로, 많은 양의 데이터를 가져올 때는 entrySet을 사용하는 것이 효율적이다.
