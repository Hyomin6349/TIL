## JSTL (JSP Standard Tag Library)

- **Core**
- Formating: 숫자나 날짜의 포맷을 지정할 때
- Functions: 문자열 조작을 위함, 문자열을 쪼개거나 나누거나
- SQL → 잘 사용하지 않음, 전체적인 코드의 구성이 깨지게 됨
- XML → 잘 사용하지 않음

<br>

## JSTL Core

```java
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>
```

- Jasper가 태그를 볼 때 출력을 위함이 아닌 행위를 위한 것임을 알아야 함

**⇒ 접두사 사용!!**

<br>

## 태그 라이브러리 만들어 보기

1. Tag 클래스를 만든다 TagSupport 클래스 상속
2. 태그 Descriptor 만들기 → WEB-INF/{파일명}.tld 로 생성
    - name: 태그의 이름
    - tagclass: 태그 클래스 경로

    → name은 다른 태그 이름과 중복될 수 있다. 태그가 식별될 수 있도록 도메인을 포함한 uri를 지정 

    → 도메인은 유일!

    → uri에 의해 tag가 유일해 지는데 태그를 사용할 때마다 uri를 붙이는 것은 너무 길기 때문에 접두사를 이용하게 된 것

<br>

## set 태그

```java
<c:set var="[변수명]" value="[값]"/>
```

- 임시 변수를 위한 set 태그
- 단일 태그

<br>

## if 태그

```java
<c:if test="${startNum!=1}">
		<a class="btn btn-prev" href="?p=${startNum-1}&t=&q=">이전</a>
</c:if>
```

- 조건문은 test 속성 안에 작성
- else 태그가 따로 없기 때문에 모두 if로 처리해 주어야 함

<br>

## fortokens 태그

```java
<c:forTokens var="fileName" items="${n.files}" delims="," varStatus="st">
	<a href="${fileName}">${fileName}</a> 
	<c:if test="${!st.last }"> / </c:if>
</c:forTokens>
```

- n.files를 , 를 구분자로 나누어 token으로 만든다
- token은 fileName이라는 변수를 사용하여 접근한다
- st.last 라는 값을 이용해서 마지막 반복문일 때는 / 를 작성하지 않는다

<br>

## format 태그

```java
<%@ taglib prefix="fmt" uri="http://java.sun.com/jsp/jstl/fmt" %>
```

```java
<fmt:formatDate pattern="yy-MM-dd" value="${n.regdate}"></fmt:formatDate>
```

- value 값을 pattern을 이용하여 formatting 해준다.

```java
<fmt:formatNumber value="${n.hit}"/>
```

- 일반적으로 통용되는 3자리씩 끊어서 보여주는 형태로 변환해준다.
- pattern 속성을 이용하여 원하는 형태로도 숫자를 넣어 줄 수 있다