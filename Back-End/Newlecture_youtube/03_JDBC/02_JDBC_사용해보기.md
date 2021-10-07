> **JDBC 사용 방법**
1. 드라이버 로드하기
2. 연결 생성하기
3. 문장 실행하기
4. 결과 집합 사용하기

⇒ 위 과정을 통해 총 4개의 객체를 생성하는데 new 연산자는 사용하지 않음, 흐름에 맞게 생성하기 때문에 그런 것임! 

(드라이버가 없는데 연결 객체를 생성하는 것.. 연결 객체가 없는데 문장 실행 객체를 생성하는 것 등등 의미가 없기 때문에)

<br>

자바 프로젝트를 생성 후 진행

1. 드라이버 로드하기 ⇒ 드라이버 객체 생성하기
    - 자바프로젝트에 Build path 추가
    - 프로젝트 우클릭 > Build path > Configure Build path..
    - 오라클에서 다운로드 한 JDBC 드라이버 jar 파일 **라이브러리에 추가**
    - 객체를 생성하는데  `class.forName()`  메서드를 이용 → 메모리 상에 드라이버가 올라가게 됨
    - 라이브러리를 추가하지 않으면 class를 불러올 수 없음!

    ```java
    class.forName("oracle.jdbc.driver.OracleDriver");
    ```

2. 연결 생성하기
    - url: 어떤 서버에 접속할 것인지
    - id: 사용자 이름
    - pw: 비밀번호

    ```java
    Connection con = DriverManger.getConnection(url, "{id}", "{pw}");
    ```

3. 문장 실행하기

    ```java
    Statement st = con.createStatement();
    ```

4. 결과 집합 사용하기
    - sql: ex) `SELECT * FROM NOTICE`
    - rs.next(); :쿼리 결과를 한 행씩 반환할 값이 있으면 true를 반환, 없으면 false를 반환
    - rs.getString("title"): 키 값에 해당하는 String value를 가져오기

    ```java
    ResultSet rs = st.executeQuery(sql);
    ```

5. 자원 반납하기

    ```java
    rs.close();
    st.close();
    con.close();
    ```