## Arrays.copyOfRange()

String의 배열 자르기는 subString 메서드를 이용해서 많이 사용했는데 다른 변수 타입 배열은 Arrays.copyOfRange()를 이용하여 자를 수 있다.

- copyOfRange(origin array, from, to)
- origin array: 자를 배열
- from: 시작 인덱스 → 포함됨
- to: 끝나는 인덱스 → 포함 안됨
- origin array: 1, 2, 3, 4, 5, from: 2, to: 4 ⇒ 3, 4