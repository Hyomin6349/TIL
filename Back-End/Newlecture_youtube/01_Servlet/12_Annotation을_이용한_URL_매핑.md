## Annotation

: 클래스나 메서드에 붙여지는 주석으로 컴파일러에 의해 사라지지 않고, 객체에 붙여 주석 정보를 활용할 수 있다. 일종의 **메타 데이터**

- Annotation을 사용하기 위해 web.xml의 metedata-complete 설정을 "false"로 바꾼다 (서블릿 3.0 이상)

    > metadata-complete="true": 모든 메타데이터 설정이 web.xml에만 있다! 다른 파일의 메타 데이터 고려하지 않는다

- URL 매핑:

```java
@WebServlet("/hi");
public class Nana extends HttpServlet{}
```

- web.xml을 통해 메타 데이터를 관리하는 것보다 Annotation을 이용하는 것이 협업 시에 더 깔끔하게 사용된다