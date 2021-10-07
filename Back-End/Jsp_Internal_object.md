## 기본 객체

- request
- response
- pageContext: 기본 객체를 얻거나  forward및 include 기능을 활용할 때 사용
- session: 클라이언트에 대한 세션 정보 처리하기 위해 사용
- application: 웹 서버, 프로젝트와 관련된 정보를 레퍼런스하기 위해 사용
- out: 출력을 위한 output 스트림을 처리할 때 사용
- config: 환경 설정에 관한 내용을 처리하기 위해 사용
- page: 현재 JSP 페이지에 대한 참조 변수에 해당
- exception: 전달된 오류 정보를 담고 있는 내장 객체

<br>

## 내장 객체 스코프

- pageContext < request < session < application

### 각 객체별 변수를 사용할 수 있는 범위

- pageContext: 현재 jsp 페이지의 메모리 영역
- **request**: 요청을 한 다음 페이지에서 사용 가능
- **session**: 인증된 사람만 사용 가능, true로 설정되어 있는 페이지 모두 다 사용 가능
- application: 어떤 제약 없이 한 어플리케이션에서 모두 사용 가능