## GET 요청

- 클라이언트는 서버에 문서를 요청한다.

    (localhost/hi ⇒ hi라는 문서를 요청한 것임)

- 문서를 요청함과 동시에 옵션을 부여할 수 있다.
- 쿼리스트링 `localhost/hi?cnt=3` 와 같은 형태
- request: 입력 도구, response: 출력 도구
- 쿼리 키워드를 읽는 메서드 `request.getParameter()` → url의 쿼리 키워드와 동일해야 하고 반환값은 ****항상 **문자열**

```java
int cnt = Integer.parseInt(request.getParameter("cnt"));
```