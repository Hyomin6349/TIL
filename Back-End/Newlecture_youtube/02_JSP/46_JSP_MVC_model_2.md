## model 1

- 컨트롤러와 뷰가 물리적으로 **분리되지 않은** 방식
- Controller: 입력과 제어를 담당
- View: 출력을 담당
- Model: 출력을 위한 데이터

<br>

## model 2

- 컨트롤러와 뷰가 **물리적으로** **분리된** 방식 → 별개의 파일로 작성
- Controller와 분리된 View를 연결하기 위해 **Forwarding**이 필요

    ⇒ **Dispatcher** 필요

- 사용자 요청이 들어오게 되면 Dispatcher가 적절한 Controller를 찾아 로직을 수행하여 View에 결과를 출력

<br>

## Forward와 Redirect

### Forward

: 현재 작업한 내용을 이어갈 수 있도록 이어가는 것

- **Request 객체를 공용 저장소로 이용**
- request.setAttribute() 메서드로 변수를 저장
- request.getAttribute() 메서드로 변수를 가져오기

Spag 서블릿

```java
req.setAttribute("result", result); //result를 request에 저장
RequestDispatcher dispatcher = req.getRequestDispatcher("spag.jsp");
dispatcher.forward(req, resp);
```

spag.jsp

```html
<body>
	<%=request.getAttribute("result") %>입니다.
</body>
```

### Redirect

: 현재 작업한 내용과는 상관없는 새로운 내용을 요청