## Response를 이용한 출력

- HttpServletResponse: 네트워크로 출력을 도와주는 객체
- OutputStream: 네트워크로 출력되는 스트림은 버퍼가 채워지면 전송되는 형태
- PrintStream: 바로바로 전송될 수 있도록하는 클래스

<br>

**binary 코드를 출력하거나 전송하고 싶을 때**

```java
import javax.servlet.*;
import javax.servlet.http.*;
import java.io.*;

pulbic class Nana extends HttpServelt{
	public void service(HttpServletRequest request, HttpServletResponse response)
											thorws IOException, ServletException
	{
			OutputStream os = response.getOutputStream();
			PrintSteram out = new PrintStream(os, true);
			out.println("Hello Servlet!!");
	}
}
```
<br>

**단순한 문자를 출력하고 싶을 때**

```java
import javax.servlet.*;
import javax.servlet.http.*;
import java.io.*;

pulbic class Nana extends HttpServelt{
	public void service(HttpServletRequest request, HttpServletResponse response)
											thorws IOException, ServletException
	{
			PrintWriter out = response.getWriter();
			out.println("Hello Servlet!!");
	}
}
```