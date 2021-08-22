- WAS에 정보를 저장하는 application 영역과 session 영역이 존재함
- application은 전역에 걸쳐 공유되는 정보
- session은 사용자마다 다른 저장 공간을 가짐
- 클라이언트에서 요청을 보낼 때 **SID(사용자 식별 아이디)**를 통해 Session에 접근할 수 있음
- 브라우저 별로 식별 아이디를 가짐

    → chrome과 IE로 접속했을 때 다른 사용자로 인식

    → 같은 chrome 브라우저라면 같은 사용자로 인식됨

<br>

## Session Method

- **setAttribute**
- **getAttribute**
- **invalidate**: 세션에서 사용되는 객체들을 바로 해제
- setMaxInactiveInterval: 세션 타임 아웃을 설정하는 메서드
- isNew: 새로 생성된 세션인지 확인하는 메서드
- getCreationTime
- getLastAccessedTime