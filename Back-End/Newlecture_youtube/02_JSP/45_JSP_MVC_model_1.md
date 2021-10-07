JSP의 코드 블럭에 출력 내용을 같이 쓰면 스파게티 코드가 될 수 있다.

```java
<!-- 입력 제어 부분 -->
<%
	String num_ = request.getParameter("n");
	int num = 0;
	if(num_ != null && !num_.equals("")) num = Integer.parseInt(num_);
%>

<!-- 출력 부분 -->
<%if(num%2!=0){%>
	홀수입니다.
<%}else { %>
짝수입니다.
<%} %>
```
<br>

코드 블럭에는 로직을 출력 부분에는 결과를 나타내는 코드만 작성하여 가독성을 높이자!

→ 로직을 담당하는 부분 = 입력과 제어를 담당 = **C**ontroller

→ 출력을 담당하는 부분 = **V**iew

→ 출력을 위한 데이터: **M**odel