Jasper가 이미 사용하고 있는 변수(**내장 객체**)를 선언하면 **중복 선언 에러**가 발생한다!

- **request, response**
- pageContext
- session
- application
- config
- out: 출력을 위한 객체 ⇒ Jasper를 사용하는 이상 out.write 를 사용하는 것은 별로...
- page: 페이지 자체!

.jsp의 코드블럭에서 **이미 정의 되어있는 내장 객체와 메서드를 이용할 수 있다**