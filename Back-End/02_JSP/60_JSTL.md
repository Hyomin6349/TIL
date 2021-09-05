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