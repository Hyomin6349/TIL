## Web Architecture

- Web Browser: client의 역역, data가 발생하는 영역
- Web Server (httpServer): client의 request (with data)를 처리하여 response
- RDBMS: 관계형 데이터베이스. client의 정보를 저장 및 조회
- Application Server: Web Server와 RDBMS의 중간 도우미
    - Business logic: Client 요청에 대한 로직 처리
    - Persistence Logic: DB와 연관된 로직
    - Presentation: Client 요청에 대한 결과, response로 반환되는 것
- WAS: Web Server + Application Server, 대표 예 tomcat
