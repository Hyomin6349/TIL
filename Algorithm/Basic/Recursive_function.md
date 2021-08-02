## 재귀 함수

: 함수 내부에서 직접 혹은 간접적으로 자기 자신을 호출하는 함수

- 메서드, 함수에 대한 정의를 명확히 해야 한다.

    → 작업 처리를 위한 **결정적 요인, 매개체값** 식별 (바뀌는 부분과 바뀌지 않는 부분을 구별) ⇒ **매개변수 설계**

- 기본 부분(끝나는 파트, basic part)과 유도 파트(재귀 파트, inductive part)로 구성된다.
- 함수 호출은 프로그램 메모리 구조에서 **스택**을 사용한다.
- 따라서 재귀 호출은 반복적인 스택의 사용을 의미하며 메모리 및 속도에서 성능저하가 발생한다. → stack overflow

<br/>

## 팩토리얼 재귀 함수

5! = 5 * 4! ⇒ factorial(5) = 5 * factorial(4)

```java
int factorial(int n){
		if(n<=1) return 1; //기저 조건
		return n * factorial(n-1);
}
```

factorial은 **n에 대한 처리만** 하고, 나머지는 toss! (단위 작업에만 집중)

<br/>

## 하노이 탑

['하노이의 탑' 이해하기](https://shoark7.github.io/programming/algorithm/tower-of-hanoi)