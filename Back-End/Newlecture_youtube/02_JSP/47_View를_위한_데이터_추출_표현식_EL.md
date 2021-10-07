## EL을 이용하여 변수 읽기

```html
<%=request.getAttribute("result") %>입니다.
<!-- EL 표기법 이용-->
${result}입니다.
```

로 변환가능하다.

- 저장소에서 꺼내는 코드 블럭을 작성하지 않고, 키값만 `${ }`형태로 작성

⇒ 출력을 위한 코드 블럭이 필요 없게 됨

<br>

## EL을 이용하여 배열 읽기

→ 배열 혹은 ArrayList와 같은 배열 포함

```html
${result[0]}
```

<br>

## EL을이용하여 Map 객체 읽기

```html
${n.title}
```