서버 측 저장소: Application, Session

<br>

**클라이언트 측 저장소:** Cookie

- 클라이언트 측에 정보를 저장하고 싶을 때 addCookie() 메서드를 이용해서 정보를 클라이언트에 넘김 ⇒ **문자열만 저장 가능**
- 브라우저에서 쿠키 정보가 있으면 그 정보와 함께 서버에 요청
- 서버는 getCookies() 메서드를 이용 ⇒ 배열 객체 반환

<br>

```java
Cookie cookie = new Cookie("c", String.valueOf(result)); //문자열만 저장 가능
response.addCookie(cookie);

Cookie[] cookies = request.getCookies();
if(cookies[0].getName().equals("result"))
		result = cookies[0].getValue();

```