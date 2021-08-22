## 방법 1

html 문서로 전달된 요청의 method를 알 수 있는 **Request 객체의** **`getMethod()`**가 있다. 이를 통해 요청된 방법이 무엇인지 판별할 수 있다.

**주의: 요청은 서버로 넘어오면서 대문자로 치환되므로, GET, POST와 비교하여 사용해야 한다.

```java
if(req.getMethod().equals("GET")) {
			
}
else if(req.getMethod().equals("POST")) {
	
}
```

<br>

## 방법 2

`super.service(req, resp)` : 전달된 요청에 따라 오버라이드된 doGet() 혹은 doPost() 메서드를 실행한다.

**doGet(), doPost()를 오버라이드하여 사용**

만약, 오버라이드 하지 않았을 경우 **405 에러 발생**

> 404: 요청된 url이 존재하지 않을 때
405: 요청하고 있는 method를 처리할 수 없을 때