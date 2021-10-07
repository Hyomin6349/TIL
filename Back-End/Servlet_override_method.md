## Servlet override method

- interface
1. destory(): 서블릿이 파괴될 때
2. init(): 서블릿이 생성될 때
3. **service(ServletRequest req, ServletResponse res)**: 클라이언트의 요청을 처리하는 메서드 → 항상 필요하겠다!
4. getServletConfig()
5. getServletInfo()

<br>

## HttpSerlvet

Servlet을 구현하면 위의 5가지의 메서드를 모두 오버라이드해야 함.

필요한 부분만 구현하여 사용할 수 있도록 

- abstract class
- 사용할 것만 구현하여 사용
- doGet(), doPost(), destroy(), service(), ...