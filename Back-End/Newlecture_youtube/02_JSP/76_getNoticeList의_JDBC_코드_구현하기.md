## getNoticeList 메서드 구현

```java
 public List<Notice> getNoticeList(String field, String query, int page)
```

- field: title 혹은 writer_id
- query: 검색어, 검색어를 포함하는 글들을 뽑아온다.
- page: 글의 수가 많을 때 page 단위로 보여주기 위한 변수

<br>

```java
String sql = "SELECT * FROM " 
				+"(SELECT ROW_NUMBER() OVER (ORDER BY REGDATE DESC) NUM, N.* "
				+ "FROM NOTICE N"
				+ "WHERE TITLE LIKE ?) "
				+ "WHERE NUM BETWEEN ? AND ?";
```

- 필터링은 정렬하기 전에 넣어주는 것이 좋다 → 서브쿼리에서 검색어 where문 작성하기
- 메인 쿼리문에서 where 절은 page 단위로 끊어주기 위함
- field를 위한 부분은 ?로 바꿔줄 수 없음

    setString(idx, STRING) 메서드는 'STRING' 형태로 `?` 가 채워지게 됨

    ⇒ sql문을 쪼개서 작성해 주어야 함

```java
String sql = "SELECT * FROM " 
				+"(SELECT ROW_NUMBER() OVER (ORDER BY REGDATE DESC) NUM, N.* "
				+ "FROM NOTICE N"
				+ "WHERE "+ field +" LIKE ? ) "
				+ "WHERE NUM BETWEEN ? AND ?";
```

- 결과를 받아올 때는 getString, getInt 메서드를 이용한다.

    → 인자로는 컬럼 인덱스나 컬럼 라벨을 사용할 수 있는데, **컬럼 라벨**을 사용하는 것을 권장

    → 컬럼 라벨의 **대소문자는 구분하지 않는다.**