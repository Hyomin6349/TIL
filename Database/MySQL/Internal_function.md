## 숫자 관련 함수

- ABS(): 절댓값
- CEILING(숫자): 올림
- FLOOR(숫자): 내림
- ROUND(숫자, 자릿수): 자릿수 기준으로 반올림
- TRUNCATE(숫자, 자릿수): 자릿수 기준으로 버림
- POW(X, Y): X의 Y승
- MOD(X, Y): X를 Y로 나눈 나머지
- GREATEST(숫자1, 숫자2, ...): 숫자 중에서 가장 큰 수 반환
- LEAST(숫자1, 숫자2, ...): 숫자 중에서 가장 작은 수 반환

> 자릿수:  1의 자리가 0, 소숫점 아래 +1, 10의 자리 이상 -1

<br>

## 문자 관련 함수

- ASCII(): 문자의 아스키 코드 값 리턴
- CONCAT(문자열1, 문자열2, 문자열3, ...): 문자열들을 결합
- INSERT(문자열, 시작위치, 길이, 새로운 문자열): 문자열의 시작 위치부터 길이만큼 새로운 문자열로 대치
- REPLACE(문자열, 기존문자열, 대체 문자열)
- INSTR(문자열, 찾는 문자열): 문자열 중 찾는 문자열의 위치 값을 리턴
- MID(문자열, 시작위치, 개수): substring과 동일
- SUBSTRING(문자열, 시작위치, 개수)
- REVERSE()
- LTRIM()
- RTRIM()
- TRIM(): 문자열의 공백 제거
- LCASE or LOWER: 소문자로 변경
- UCASE or UPPER: 대문자로 변경
- LEFT(문자열, 개수): 왼쪽에서 개수만큼 추출
- RIGHT(문자열, 개수): 오른쪽에서 개수마큼 추출

> 문자열의 위치: 제일 왼쪽, 1부터 시작!!

<br>

## 날짜 관련 함수

- NOW() SYSDATE() CURRENT_TIMESTAMP(): 현재 날짜와 시간 리턴
- CURDATE() CURRENT_DATE(): 현재 날짜 리턴
- CURTIME() CURRENT_TIME(): 현재 시간 리턴
- DATE_ADD(날짜, INTERVAL 기준 값): 기준값 만큼 더하기
- DATE_SUB(날짜, INTERVAL 기준 값): 기준값 만큼 빼기
- YEAR(): 날짜의 연도 리턴
- MONTH()
- MONTHNAME(): 월을 영어로 리턴
- DAYNAME(): 날짜의 요일을 영어로 리턴
- DAYOFMONTH(): 날짜의 월별 일자 리턴
- DAYOFWEEK(): 날짜의 주별 일자 리턴 → 일요일(1), 월요일(2) ... 토요일(7)
- WEEKDAY() → 일요일(0), 월요일(1) ... 토요일(6)
- DAYOFYEAR(): 일년을 기준으로 한 날짜까지의 일 수
- WEEK(): 일년 중 몇 번째 주
- FROM_DAYS(날 수): 날 수만큼 경과한 날의 날짜 리턴, ex) 100일 후
- TO_DAYS(날짜): 날짜까지의 일 수 리턴, ex) 21-09-06일로 부터 며칠이 지났나
- DATE_FORMAT(날짜, 형식): 날짜를 형식에 맞게 리턴

<br>

## 그룹 관련 함수

- COUNT(필드명): 반환되는 레코드의 수를 리턴
- SUM(필드명): 필드에 해당하느 값을 함친 값을 리턴
- AVG(필드명)
- MAX(필드명)
- MIN(필드명)