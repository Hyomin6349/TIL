## Servlet 실행

- 사용자에게 class 명으로 접근하여 실행하도록 하면 안됨
- 해당 servlet 코드와 mapping되는 url을 설정해 주어야 한다. ⇒ 사용자에게 제공되는 servlet 이름

예) Nana Servlet (Nana.class), url: /hello 

 ~/hello로 요청이 들어왔을 때, WAS는 hello와 매핑되는 Nana class를 실행한다.

 <br>

## Servlet 실행 방법

- WEB-INF는 클라이언트가 접근할 수 없는 디렉토리

    → 클래스 파일이나, 사용자가 접근하면 안 되는 파일들을 넣어 놓는다.

1. ROOT>WEB-INF에 생성한 .java 파일을 컴파일한 후 이동시킨다.
2. ROOT>WEB-INF>web.xml에서 url mapping 부분을 넣는다.

```xml
<servlet>
		<servlet-name>na</servlet-name>
		<serlvet-class>Nana</servlet-class>
</servlet>

<servlet-mapping>
		<servlet-name>na</serlvet-name>
		<url-pattern>/hello</url-pattern>
</servlet-mapping>
```

1. 톰캣 서버 재실행 후 /hello 로 실행
2. 파일이 없으면 WAS에 넘겨, WAS가 url 매핑 후 실행해 줌