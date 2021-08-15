Cookie가 가진 정보는 서블릿마다 다르다

→ 모든 쿠키를 모든 서블릿에 대해 동일하게 전송하고 받는다면

→ 쿠키 간의 이름 충돌, 비효율성 문제가 야기될 것이다.

⇒ 쿠키에게 **url을 설정**해 주어 해당 Servlet에만 정보를 보내도록 한다! 

⇒ **setPath()** 메서드 사용

<br>

```java
valueCookie.setPath("/");//모든 url
valueCookie.setPath("/notice/");//notice가 포함된 하위 url 까지
valueCookie.setPath("/calc2"); //매칭된 url만
```