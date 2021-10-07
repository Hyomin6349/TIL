1. Webcontent 에 jsp 파일을 추가한다
2. jsp 파일 이름은 바로 url과 매핑되므로 소문자로 작성하는 것이 좋다!
3. 기본적인 html 코드와 출력에 대한 웹 문서 설정 코드가 추가되어 있다

    ```java
    <%@ page language="java" contentType="text/html; charset=UTF-8"
        pageEncoding="UTF-8"%>
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="UTF-8">
    <title>Insert title here</title>
    </head>
    <body>

    </body>
    </html>
    ```

4. body 태그 안에 작성되는 내용은 출력문으로써 잘 출력된다
5. 반복문을 추가해보자

    → 반복문의 범위를 중괄호로 표기해야 하고 이는 코드 블럭으로 감싸야 한다

    ```java
    <% for(int i=0;i<10;i++) {%>
    	안녕 서블릿 <br>
    <% }%>
    ```

6. 반복문에 멤버 변수를 사용해보자

    ```java
    <%@ page language="java" contentType="text/html; charset=UTF-8"
        pageEncoding="UTF-8"%>
        
        
    <%
    	int cnt = 100;
    	String cnt_ = request.getParameter("cnt");
    	if(cnt_ != null && !cnt_.equals("")) cnt = Integer.parseInt(cnt_);
    %>
    <!DOCTYPE html>
    <html>
    <head>
    <meta charset="UTF-8">
    <title>Insert title here</title>
    </head>
    <body>
    	<% for(int i=0;i<cnt;i++) {%>
    	안녕 서블릿 <br>
    	<% }%>
    </body>
    </html>
    ```