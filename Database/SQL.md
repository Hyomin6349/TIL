## SQL (Structured Query Language)

- Database에 있는 정보를 사용할 수 있도록 지원하는 언어
- 모든 DBMS에서 사용 가능
- **대소문자 구별하지 않음, 단 데이터의 대소문자는 구분**
- DCL, DDL, DML, TCL 로 구분

⇒ USER는 SQL을 이용하여 DBMS를 통해 Database에 접근한다.

<br>

### DML

: 데이터를 조작하는 언어

- **INSERT**
- **UPDATE**
- **DELETE**
- **SELECT**

### DDL

: 테이블의 구조를 조작하는 언어 (생성, 삭제, 수정)

- CREATE
- ALTER
- DROP
- RENAME

### DCL

: 데이터 베이스에 대한 접근 권한

- GRANT
- REVOKE

### TCL

: 트랜잭션 제어어

- COMMIT
- ROLLBACK

<br>

## 데이터 타입

- CHAR: 고정 길이, 실제 저장된 데이터 크기와 상관없이 할당된 데이터 영역만큼 차지
- VARCHAR: 가변 길이, 실제 저장된 데이터 크기의 영역 차지, 최대 공간 크기를 지정
- INT
- DOUBLE(M, D)
- DATETIME: 현재 위치의 시간으로 고정된 시간
- TIMESTAMP: TIMEZONE에 영향을 받는 시간
- BLOB: 사진이나 동영상을 저장하기 위함