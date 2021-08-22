## Servlet

= 자바 서버 어플리케이션 만들기

- 기능 별로 코드가 나뉘어 있어 기능 별로 코드가 선택적으로 **선택되어 실행**됨

    ⇒ 조각난 서버 어플리케이션 = Servlet

- 필요한 기능 하나씩 만들면 됨

<br>

## Servlet 코드 작성과 실행

- 서블릿 코드는 WAS 에 의해 load, 실행됨
- WAS는 사용자 정의 클래스명으로 접근하는 것이 아닌 **약속되어 있는 클래스명 혹은 인터페이스명으로 접근 (**예: HttpServlet**)**
- 정해져 있는 **서비스 함수**를 실행 (service())

<br>

Nana Servlet 만들기

```java
import javax.servlet.*;
import javax.servlet.http.*;
import java.io.*;

pulbic class Nana extends HttpServelt{
	public void service(HttpServletRequest request, HttpServletResponse response)
											thorws IOException, ServletException

	{
			System.out.println("hello Servlet");
	}

}
```