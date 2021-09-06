## IN CLUASE

- 여러 값을 OR 관계로 비교하는 경우에 사용
- 예) 취미가 축구, 야구, 농구인 사람들을 고르시오

```java
select * from people 
where hobby = '축구' 
or hobby = '야구'
or hobby = '농구' ;
```

```java
select * from people where hobby in ('축구', '농구', '야구');
```

- in 안의 하나 이상과 일치하는 경우 조건에 맞는 것으로 평가
- or 연산자를 반복해서 사용하는 경우보다 in을 사용하는 것이 직관적이고, 연산자의 수도 줄어든다
- in 연산자가 or 연산자보다 실행 속도가 빠르다
- in 연산자 안에 서브쿼리를 넣을 수 있다.