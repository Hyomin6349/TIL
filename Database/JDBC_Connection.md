## 자바와 DB를 연결하는 순서

1. Driver Loading

** Driver: 데이터베이스 회사들이 자기들의 db를 사용할 수 있도록 만들어 놓은 클래스 모음 → jar 파일, 우리는 드라이버를 사용하면 된다. 내부 동작 과정을 알 필요가 없다

1. Connection 준비

    : db와의 연결을 도와주는 인터페이스

2. Statement 준비

    : 쿼리문 실행을 도와주는 인터페이스

    - 쿼리문에 `?` 가 없는 경우

        ⇒ **Statement** 사용

    - 쿼리문에 `?` 가 있는 경우

        ⇒ **PreparedStatement** 사용

         `setString([column_index], [value]), setInt() ...` 와 같은 메서드를 이용하여 `?` 채우기

    - update, delete 문 실행

        ⇒ `executeUpdate();` 메서드를 사용, 메서드의 반환 값은 변경된 column의 개수

        ** 기본적으로 autocommit이 활성화되어 있다.

    - select 문 실행

        ⇒ `executeQuery();` 반환값은 **ResultSet** 

3. ResultSet 활용
    - `rs.next()`: 다음 레코드가 있으면 true 반환
    - `getString([column_label]), getInt(), ...` 컬럼 라벨이나 컬럼 인덱스로 반환 값 받아오기

4. 사용한 자원 반환하기: close() 메서드 이용 → 생성한 자원의 역순으로 반환
    - finally에서 자원을 반납하는 경우

        ```java
        finally{
        	try {
        			if(rs != null) rs.close();
        			if(pst != null)	pst.close();
        			if(con != null) con.close();
        		} catch (SQLException e) {
        			// TODO Auto-generated catch block
        			e.printStackTrace();
        		}

        }
        ```

    - 클래스의 static 메서드로 분리하여 사용
    - AutoCloseable 인터페이스를 사용하는 경우 (Connection, Statement, ResultSet 모두 AutoCloseable 인터페이스 상속)

        ```java
        public static void close (AutoCloseable...autoCloseable) { //... 가변 인자 변수
        		for(AutoCloseable ac : autoCloseable) {
        			if(ac!=null)
        				try {
        					ac.close();
        				} catch (Exception e) {
        					// TODO Auto-generated catch block
        					e.printStackTrace();
        				}
        		}
        	}
        ```