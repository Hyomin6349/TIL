## 트랜잭션

: 데이터베이스의 상태를 변화시키는 일종의 작업 단위를 의미

- START TRANSACTION: COMMIT, ROLLBACK이 나올 때까지 실행되는 모든 SQL
- COMMIT: 모든 코드를 실행
- ROLLBACK: START TRANSACTION 실행 전 상태로 되돌림
- SAVEPOINT: 임시 저장
- ROLLBACK TO ~: save point까지 롤백