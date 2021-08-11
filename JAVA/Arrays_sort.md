## 오름차순

```java
Arrays.sort(arr);
```
<br>

## 내림차순

```java
Arrays.sort(arr, Collections.reverseOrder());
```

<br>

## 일부분만 정렬

```java
Arrays.sort(arr, start_idx, last_idx);
```

<br>

## 객체 배열 정렬

- 객체는 **Comparable 인터페이스**를 구현한 클래스여야 함
- **compareTo() 메서드**를 오버라이드 해야 함

```java
Person[] persons = new Person[10];
Arrays.sort(persons);
Arrays.sort(persons, Collections.reverseOrder());
```

<br>

## comapareTo()

- 오름차순 정렬:  `return age - target.age`
- 내림차순 정렬:  `return target.age - age`

<br>

## Arrays.sort의 시간복잡도

- DualPivotQuicksort.sort() 를 사용하여 최악의 경우에도 $O(n * logn)$의 시간복잡도를 가진다
- 사실 배열의 크기마다 sort를 다르게 하여 동작한다
- 크기에 따라 효율적인 sort를 선택해 수행한다고 생각하면 되겠다..

[[ JAVA ] Arrays.sort()의 내부 동작(1)](https://javanitto.tistory.com/6)