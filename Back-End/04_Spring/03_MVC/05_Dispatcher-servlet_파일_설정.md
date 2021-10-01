## Spring에게 Servlet을 맡기자

**⇒ web.xml 파일은 모든 url에 대한 요청을 받아드려 dispatcher에 전달**

**⇒ dispatcher은 url 마다 매핑 정보를 가지고 해당하는 리소스에 요청!**

<br>

- Annotation을 통한 url이 mapping이 불가능해짐 → **xml을 통해 mapping!**
- web.xml 파일에 servlet 추가
    
    ```xml
    <servlet>
    	<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    </servlet>
    ```
    
- url mapping 정보 설정하기
    
    → 만드는 Dispatcher는 Front Controller로 **모든 url**을 받아온다
    
    → servlet name을 통해 url과 servlet class 연결하기
    
    - `/*` : 모든 url dispatcher에 요청, mapping 정보 없으면 error 반환
    - `/` : 모든 url을 dispatcher에 요청하고 없으면 직접 리소스에 접근
    
    ```xml
    <servlet>
    	<servlet-name>dispatcher</servlet-name>
    	<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    </servlet>
    <servlet-mapping>
    	<servlet-name>dispatcher</servlet-name>
    	<url-pattern>/</url-pattern>
    </servlet-mapping>
    ```
    
- WEB-INF 안에 **[servlet-name]-servlet.xml** 파일을 추가한다 → 만든 servlet-name 에 해당하는 이름에 맞게 파일을 생성해야 함 (예약어)
- dispatcher-servlet.xml **bean 태그**를 이용하여 url mapping 정보 작성
    - id: url
    - class: 패키지 명을 포함한 매핑 클래스명
    
    ⇒ id에 해당하는 url이 요청될 시 class를 객체화하여 호출
    
    ⇒ 객체화된 클래스는 IoC 컨테이너에 담김
    
    ```xml
    <bean id="/index" class="com.newlecture.web.controller.IndexController.java">  
    </bean>
    ```
    
- 각 Controller 클래스는 **handleRequest 메서드**를 구현하여 해당 요청을 수행
    
    → Controller 인터페이스 구현
    
    ```java
    public class IndexController implements Controller{
    
    	@Override
    	public ModelAndView handleRequest(HttpServletRequest request, HttpServletResponse response) throws Exception {
    		
    		ModelAndView mv = new ModelAndView();
    		mv.addObject("data", "MVC");
    		mv.setViewName("index.jsp");
    		
    		return mv;
    	}
    
    }
    ```