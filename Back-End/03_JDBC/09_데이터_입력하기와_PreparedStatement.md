```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Date;

public class Program {

	public static void main(String[] args) throws ClassNotFoundException, SQLException {
		
		String title = "TEST2";
		String writerId = "hyomin";
		String content = "hahaha";
		String files = "";
		
		String url = "jdbc:oracle:thin:@localhost:1521/xepdb1";
		String sql = "insert into notice(" + 
				"    title," + 
				"    writer_id," + 
				"    content," + 
				"    files" + 
				") values (?, ?, ?, ?)";
		
		Class.forName("oracle.jdbc.driver.OracleDriver");
		Connection con = DriverManager.getConnection(url, "hyomin", "1234");
		//Statement st = con.createStatement();
		PreparedStatement st = con.prepareStatement(sql);
		st.setString(1, title);
		st.setString(2, writerId);
		st.setString(3, content);
		st.setString(4, files);
		int result = st.executeUpdate();
		
		System.out.println(result);
		
		st.close();
		con.close();
	}

}
```

- 변수를 통해 insert 쿼리문을 작성할 때 직접 변수를 대입하면 작성이 복잡해짐
- PrepareStatement를 이용하면 변수 부분을 ?로 대체하고 후에 넣어줄 수 있음
- 넣는 변수 타입에 따른 메서드를 호출함
- select문은 executeQuery() 메서드를 이용
- delete, insert, update 문은 executeUpdate() 메서드를 이용
- 메서드의 타입을 잘 구분해 주어야 함! ⇒ PreparedStatement OR Statement