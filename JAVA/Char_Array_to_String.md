## String 생성자 이용하기

```html
char[] ch = {'a', 'b', 'c', 'd'};
String str = new String(ch);
```

<br>

## String.valueOf 이용하기

```html
char[] ch = {'a', 'b', 'c', 'd'};
String str = String.valueOf(ch);
```

<br>

## StringBuilder 이용하기

문자하나하나를 돌면서 SB에 넣고 프린트 → 비추