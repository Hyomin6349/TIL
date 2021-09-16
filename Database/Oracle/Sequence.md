## Sequence

- **유일한 값**을 생성해주는 오라클 객체
- primary key를 생성하기 위해 주로 사용됨
- 순차적으로 증가하는 컬럼을 자동적으로 생성한다
- 시퀀스는 테이블과 독립적으로 저장되고 생성된다

<br>

## 생성 방법

```sql
CREATE SEQUENCE hyomin."NOTICE_ID_SEQ"
MINVALUE 1 MAXVALUE 999999 
INCREMENT BY 1 
NOORDER 
NOCYCLE 
;
```

- 캐시: 데이터를 항상 새롭게 가져오면 시간이 많이 걸리기 때문에 캐시에 저장해두고 사용하는 옵션, 가져오는 데이터가 중복이 잦은 경우에 유용
- CYCLE(주기): max까지 sequence를 사용한 경우에 다시 1부터 사용할 것인가
- ORDER(정렬): sequence가 정렬된 상태를 보장할 것인가

<br>

## 사용

테이블의 값과 시퀀스를 연결한다

1. sqldeveloper 접속
2. 테이블의 편집 버튼 누르기
3. 컬럼 지정 후 하단의 ID 열 탭 클릭
4. 열 시퀀스 유형으로 하여, 생성해둔 시퀀스와 연결