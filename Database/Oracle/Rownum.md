## ROWNUM

: 조회된 결과에 순번을 매겨줌

 order by 절이 실행되기 전에 **where 절이 실행되면서** 순번이 매겨지기 때문에 order by 절과 함께 쓰이면 순번이 다시 뒤섞인다.

### 해결법

1. 서브 쿼리를 이용한다
2. ROW_NUMBER()을 사용한다
>> select row_number() over (order by ~)