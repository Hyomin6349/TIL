## HTTP 프로토콜

- connectionless
- stateless
- 매 요청마다 클라이언트가 누구인지 매번 확인해야 함
- 이러한 단점을 보완하기 위해 Cookie와 Session 사용

<br>

## Cookie

- Client 단에 저장되는 정보
- 사용자가 별도의 요청을 하지 않아도 브라우저는 request시 Request Header에 넣어 자동으로 서버에 전송
- Browser마다 저장되는 쿠키가 다름 → Browser가 다르면 다른 사용자로 인식
- 서버에서 사용자의 컴퓨터에 저장하는 **정보파일 ⇒** key, value쌍의 String 형태
- 사용 목적
    - 세션 관리: 사용자 아이디, 접속시간, 장바구니 등의 서버가 알아야 할 정보 저장
    - 개인화: 맞춤 광고와 같이 개인에 맞춘 페이지
    - 트래킹: 사용자의 행동과 패턴을 분석하고 기록
- 구성 요소
    - **key - value**
    - 유효기간
    - 도메인
    - 경로: 쿠키를 전송할 요청 경로
- 동작 순서
    1. Client가 페이지를 요청
    2. WAS는 Cookie를 생성
    3. HTTP Header에 Cookie를 넣어 응다
    4. Browser는 넘겨받은 Cookie를 PC에 저장, 요청시 Cookie와 함께 전송
    5. Browser가 종료되어도 만료기간이 남아있다면 Cookie 보관되어, 동일 사이트 재방문시 요청페이지와 쿠키 함께 전송
- javax.servlet.http.Cookie
    - 생성: `Cookie cookie = new Cookie(String name, String value)`
    - 값 변경/얻기: `cookie.setValue(String value)/ cookie.getValue();`
    - 도메인, 경로 변경/얻기
    - 유효기간 지정/얻기: `cookie.setMaxAge(0);//삭제 cooke.getMaxAge();`
    - 생성된 cookie를 client에 전송: `response.addCookie(cookie);`
    - client에 저장된 cookie 얻기: `Cookie[] cookies[] = request.getCookies();`
    
<br>

## Session

: 방문자가 웹 서버에 접속해 있는 상태 (하나의 단위로써)

- **WAS의 memory에 Object의 형태**로 저장
- 동작 순서
    1. 클라이언트가 페이지를 요청
    2. 서버는 접근한 클라이언트의 Request-Header 필드인 Cookie를 확인하여, 클라이언트가 해당 session-id를 보냈는지 확인
    3. session-id가 존재하지 않는다면, 서버는 session-id를 생성해 클라이언트에게 돌려준다
    4. 서버에서 클라이언트로 돌려준 session-id를 쿠키를 사용해 서버에 저장 (JSESIONID)
    5. 클라이언트는 재접속 시, JSESIONID를 이용하여 session-id 값을 서버에 전달
- 특징
    - 웹 서버에 저장되는 쿠키 (=세션 쿠키)
    - 브라우저를 닫거나, 서버에서 세션을 삭제 했을 때만 삭제가 되므로, 쿠키보다 보안이 좋다
    - 저장 데이터에 제한이 없다 (Object 형태로 저장, 메모리 공간만큼 저장 가능)
    - 동접자 수가 많으면 서버 메모리에 과부하가 올 수 있음
    - **각 클라이언트에 고유 Session ID를 부여**하여 각 클라이언트 요구에 맞는 서비스 제공
- HttpSession
    - 생성: `HttpSession session = request.getSession();`
    - 값 저장: `session.setAttribute(String name, Object Value);`
    - 값 얻기: `Object obj = session.getAttribute(String name);`
    - 값 제거: `session.removeAttribute(String name), session.invalidate();`
    
<br>

## Cookie와 Session의 차이

- 세션도 결국 Cookie를 사용함, 다만 Session은 서버단에 저장하여 사용, Cookie는 클라이언트 단에 저장하여 사용
- 쿠키는 만료시간이 지날때까지 파일 형태로 정보 저장 반면, 세션은 만료 시간은 서버측에서 설정하고 브라우저가 닫히면 만료시간에 상관없이 삭제
- 쿠키는 클라이언트 로컬에 저장되어 보안에 취약하지만, 세션은 sessionid만 쿠키에 저장하기 때문에 보안성이 더 좋음
- 세션은 서버의 처리가 필요하기 때문에 쿠키보다 속도가 느림
- 세션을 많이 사용하면 서버의 메모리가 감당할 수 없어질 때가 있고 속도가 느려질 수 있음
