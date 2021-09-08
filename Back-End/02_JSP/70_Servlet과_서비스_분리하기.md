공지사항 페이지가 제공하는 서비스

- 공지사항 작성 → 관리자
- 공지사항 열람 가능 여부 → 관리자
- 공지사항 수정 → 관리자
- 공지사항 삭제 → 관리자
- 공지사항 목록 조회
- 공지사항 상세 조회
 
<br>

공지사항 목록 조회 서비스를 제공하기 위한 메서드

- getNoticeList()
- getNoticeList(int page)
- **getNoticeList(String field, String query, int page) → 구현**
- getNoticeCount()
- **getNoticeCount(String field, String query) → 구현**
- **getNotice(int id)**
- **getPrevNotice(int id)**
- **getNextNotice(int id)**

⇒ 이름이 같은 메서드는 같은 기능을 하는 메서드들이다. 

⇒ 모두 따로 구현할 필요 없이 제약 조건이 가장 많은 즉, **인자가 가장 많은 메서드를 구현**하고 이를 사용하여 나머지 함수를 구현하자!