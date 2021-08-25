## Math.round()

: 소수점 첫번째 자리를 반올림 하여 정수로 리턴시켜주는 메서드

```jsx
double d1 = 3.5;
print(Math.round(d1)); //4 출력
```

<br>

- 소수점 N번째 자리에서 반올림하기

    소수점 N번째를 소수점 첫번째로 만들고 Math.round() 연산

    ```jsx
    double d1 = 3.456;
    print(Math.round(d1*100)/100); // 3.45 => 345.6 => 346 => 3.46 
    ```

- Math.ceil(): 올림
- Math.floor(): 내림

<br>

## String.format()

```jsx
double pie = 3.141592;
print(String.format("%.2f", pie)); //소수점 2째 자리까지 출력 => 3째 자리에서 반올림
print(String.format("%.3f", pie)); // 3.142
```

<br>

## Math.round()와 String.format()의 차이점

- Math.round()는 소수점 아래가 0일 때 출력하지 않음 ⇒ 정수형 리턴이라!
- String.format()은 소수점 아래가 0일 때도 출력 ⇒ 문자열이라!

[[Java] 자바 소수점 n번째 자리까지 반올림하기](https://coding-factory.tistory.com/250)