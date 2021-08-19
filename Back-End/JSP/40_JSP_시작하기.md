## JSP

: HTML에 Java 코드를 편리하게 적을 수 있도록 도와주는 것

정적인 HTML 문서에 동적인 요소를 추가하기 위해 JSP가 사용된다.

기존의 html 문서의 확장자 명을 .jsp로만 변경하면 된다.

<br>

## Jasper

JSP 엔진 중 하나로 jsp 문서를 읽는 역할. 

JSP가 호출 되면, Jasper가 동작하고 jsp 파일을 **Servlet으로 컴파일**한다.

> **[Jasper의 작업공간]**
.metadata → .plugins → org.eclipse.wst.server.core → tmp0→ work → Catalina → localhost → 프로젝트명 → org → apache → jsp

<br>

```java
JSP파일이 브라우저에 바로 띄워지는 것이 아니라, 호출된 JSP파일을 Jasper가 컴파일 후 다시 HTML에 그려주는 것.

이것이 우리가 브라우저에서 호출한 JSP가 화면에 나타나는 과정입니다.
```

<br>

[JSP를 서블릿으로 변환시켜주는 Jasper](https://thisisnew-storage.tistory.com/6)