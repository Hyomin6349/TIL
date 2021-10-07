## 개발자 모드의 Network tab

어떤 데이터가 어떻게 전달되고 있는지 볼 수 있다.

<br>

## 400번대 에러

- 404에러: 매칭되는 url이 없는 경우
- 405에러: url은 있지만 요청을 처리할 메서드가 없는 경우
- 403에러: url과 메서드는 있지만 권한이 없는 경우

<br>

## 다중 POST 값 받기

```java
String[] openIds =  req.getParameterValues("open-id");
```

- 배열 객체로 받는다
- getParameterValues 메서드 이용