## 설정 파일 분리하기

- 프로젝트의 사이즈가 커짐에 따라 한 곳에 모든 설정을 넣는 것이 아닌
- 서비스, 서블릿, 보안으로 설정을 분리하여 관리하는 것이 좋다
- **기존의 dispatcher-servlet은 web.xml에서 설정 파일이 어디에 위치하는지 명시하지 않았기 때문에 예약어로 사용해야 했다.**
- 위치와 설정 파일의 이름을 바꾼다면 따로 설정 파일 경로를 명시해 주어야 한다

```xml
<servlet>
	<servlet-name>dispatcher</servlet-name>
	<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
	<init-param>
		<param-name>contextConfigLocation</param-name>
		<param-value>
			/WEB-INF/spring/servlet-context.xml
		</param-value>
	</init-param>
	<load-on-startup>1</load-on-startup>
	<async-supported>true</async-supported>
</servlet>
```

- init-param: 설정 파일의 위치를 알려준다
- param-name의 contextConfigLocation은 예약어
- param-value: web root에서 시작하는 설정 파일의 경로를 작성한다
- servlet 객체가 메모리에 올라가는 시점: **url 요청이 온 첫 순간 →** 느리다
- load-on-startup: tomacat이 load 됐을 때 메모리에 올린다, 우선 순위 지정 가능
- async-supported: 비동기적으로 메모리에 올린다

<br>

### 두 개 이상의 설정 파일이 있을 때

```xml
<listener>
	<listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
</listener>
<context-param>
	<param-name>contextConfigLocation</param-name>
	<param-value>
			/WEB-INF/spring/security-context.xml
			/WEB-INF/spring/service-context.xml
	</param-value>
</context-param>
```

- listener: tomcat이 시작될 때, tomcat이 끝날 때, 세션이 시작, 종료될 때 등의 시점에 사용할 수 있는 이벤트 리스너
- ContextLoader를 DispatcherServlet이 이용할 수 있음
- ContextLoader를 이용하여 다른 설정 파일도 추가한다.