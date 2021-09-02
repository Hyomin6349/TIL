## Ajax (Asynchronous Javascript And XML)

- 언어나 프레임워크가 아닌 **구현하는 방식**
- 웹에서 화면을 갱신하지 않고 데이터를 서버로부터 가져와 처리하는 방법
- JavaScript의 XMLHttpRequest 객체로 데이터를 전달하고 **비동식 방식**으로 결과를 조회
- 화면 갱신이 없으므로 사용자 입장에서는 편리하지만, **동적**으로 DOM 구성해야 함

**XMLHttpRequest: 자바스크립트가 Ajax 방식으로 통신할 때 사용하는 객체

<br>

## 요청과 응답

- data를 입력 후 **이벤트** 발생
- 서버에서 요청을 처리한 후 Text(간단 응답), XML 혹은 JSON (복잡한 응답)으로 응답

    → 일반 요청은 페이지가 전환되며 결과 보여줌

- 클라이언트에서는 응답 data를 이용하여 **화면 전환 없이 현재 페이지에서 동적으로 화면 재구성**

<br>

## jQuery Ajax

- `$.ajax(options);`
- options
    - url: 대상 url
    - data: 요청 매개변수 지정
    - type: GET, POST 방식 지정 ⇒ `$.get()`, `$.post()`
    - success:function(data, status, xhr): Ajax 성공 이벤트 리스너
    - error:function(data, status, xhr): Ajax 실패 이벤트 리스너

    → 여러개의 옵션을 넣어줄 때는 JSON 형식으로 넘겨주면 됨

- `$.get(url, function())`: 위의 형식을 줄여서 써준 형태

<br>

## CSV (Comma Separated Values)

: 각 항목을 쉼표로 구분해 데이터를 표현하는 방법

- 데이터 표현 방식이 짧아 많은 양의 데이터 전송 시 유리 → 속도 유리
- 각 항목이 어떤 내용에 대한 데이터인지 파악하기 어렵다 → 항상 같은 구조의 데이터를 주고 받을 때 유리