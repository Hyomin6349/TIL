## 서브 쿼리

: 쿼리의 내부에 포함되어 있는 **select 문**

- 비교 연산자의 **오른쪽**에 작성해야 한다
- **반드시 괄호로 감싸져 있어야 한다**
- 단일 행 또는 다중 행 비교 연산자와 함께 사용된다
- 중첩 서브 쿼리 (Neste Subquery): Where 문에 작성되는 서브 쿼리
    - 단일 행: =, >, < 로 비교할 수 있는 하나의 결과 값이 리턴되는 쿼리 문
    - 복수 행: 두 개 이상의 결과가 나오는 쿼리 문 → **in, any, all을 이용**

        > in: 여러 개의 결과 중에 원하는 값이 있을 때
        any: 여러 개의 결과 중에 **하나라도** 조건을 만족할 때
        all: 여러 개의 결과 **모두**에 대해 조건을 만족할 때

    - 다중 컬럼: `(col1, col2, ...) in (val1, val2, ...)` 로 조건 처리
- 인라인 뷰 (Inline View): From 절에 작성되는 서브 쿼리로 테이블로 이용하는 쿼리
- 스칼라 서브 쿼리 (Scalar Subquery): Select 문에 작성되는 서브 쿼리
- 서브 쿼리가 가능한 곳: select, from, where, having, order by, update문의 set, insert 문의 values
- create에서 서브 쿼리를 이용하여 테이블을 생성할 수 있다.

    ```sql
    --예) employee의 구조를 복사해서 테이블을 만들 때
    create table temp
    select * from employee
    where 1=0;
    ```

- insert에서 서브 쿼리를 이용할 수 있다.

    ```sql
    insert temp
    select * from employee
    where department_id=80;
    ```