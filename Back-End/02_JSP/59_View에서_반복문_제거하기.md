데이터베이스에서 컬럼을 꺼내올 때마다 반복해서 list를 출력하는 구문이 있었다

```html
<% 
List<Notice> list=  (List<Notice>)request.getAttribute("list");
for(Notice n: list) {
	pageContext.setAttribute("n", n);
%>
<tr>
	<td>${n.id}</td>
	<td class="title indent text-align-left"><a href="detail?id=${n.id}">${n.title}</a></td>
	<td>${n.writer_id}</td>
	<td>${n.regdate}</td>
	<td>${n.hit}</td>
</tr>
<%} %>
```

이 또한 스파게티 코드라고 할 수 있다

⇒ 반복문을 위한 태그를 사용해보자!

<br>

## JSTL

1. jstl을 다운로드 받는다

[](https://mvnrepository.com/artifact/javax.servlet/jstl/1.2)

1. 프로젝트의 WEB-INF>lib에 jar파일을 옮긴다
2. jsp 파일에 태그 라이브러리 추가

    ```html
    <%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
    ```

3. 반복문 대신에 태그 사용하기

    ```html
    <c:forEach var="n" items="${list}">
    ```

    - 저장소에 담겨있는 list에 대해 반복문을 수행
    - 각 아이템을 n 변수라고 부른다.