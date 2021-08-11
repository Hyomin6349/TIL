## Lambda Expression

- 기본 사용법: `(매개변수, ... ) -> {실행문 ... }`

<br>

## functional interface

: 1개의 추상 메서드만 가진 인터페이스

⇒ 람다 표현 가능

ex) Comparator

```java
Collecions.sort(list, new Comparator<Person>(){
	@Override
	public int compare(Person o1, Person o2){
		return o1.age - o2.age
	}
})
```

위의 코드를 람다식으로 변경 (functional interface이기 때문에 가능한 것임)

```java
Collections.sort(list, (o1, o2) -> {o1.age - o2.age})
```