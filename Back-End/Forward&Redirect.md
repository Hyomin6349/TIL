## forward

```java
RequestDispatcher dispatcher = 
									request.getRequestDispatcher(path);
dispatcher.forward(request, response);
```

- 동일 서버 (프로젝트) 내의 경로로 이동 → **path에 context root 하위 경로를 입력**
- 기존 URL 유지
- 기존의 request와 response가 그대로 전달
- redirect에 비해 빠름
- request에 데이터를 담아 전달 가능

<br>

## redirect

```java
response.sendRedirect(location);
```

- 동일 서버 포함 타 URL 가능 → http 부터 시작하는 경로 작성
- 이동하는 page로 변경
- 기존의 request와 response는 소멸되고 새로운 request와 response 생성
- forward에 비해 느림
- session 혹은 cookie를 사용하여 데이터 전달