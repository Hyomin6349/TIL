## Servlet과 JSP를 이용한 프로그래밍

- JSP으로 View를 구현
- Servlet으로 Controller 구현
- 각 Servlet이 별도의 Dispatcher를 구현했음 → 비효율적

    ⇒ 순수하게 Controller 구현을 POJO(Plain Old Java Object) 로 구현하여 Dispatcher와 분리

<br>

## Dispatcher의 기능

- Servlet의 기능을 차단
- 모든 url으로 부터 넘어온 입력 값을 POJO가 사용하기 쉽게 전달
- Controller에게 뷰 페이지 정보를 return 받아 jsp에 forwarding
- **Controller와 WAS의 결합력을 낮춤 → 다양한 환경에서의 이식성을 높임**

⇒ Spring 프레임워크가 Dispatcher의 기능을 도와준다! (Front Controller)

<br>

## Spring MVC

- Spring이 Front Controller의 기능을 도와준다 ⇒ **Dispatcher Servlet**
- url 마다 매핑되는 설정 파일을 이용하여 Controller에 요청
- POJO (Controller) 들은 model과 view에 대한 정보를 반환한다
- 반환된 정보를 바탕으로 view에 model을 전달