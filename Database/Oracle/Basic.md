## 설치

1. 오라클 무료 버전 파일 다운로드

[Oracle Database Express Edition (XE) Downloads](https://www.oracle.com/database/technologies/xe-downloads.html)

1. 관리자 권한으로 실행
2. 중간에 비밀번호는 기억할 수 있는 번호로 넣기!
3. CMD에서 접속하기

    ```java
    >> sqlplus "/as sysdba"
    ```

<br>

## 계정 생성 및 권한 부여

```java
>> create user c##[id] identified by "[pw]";
>> grant connect, resource, dba to [id]; //모든 권한을 부여한 것
```

<br>

## 테이블 생성하기

기본 mySQL 문법과 같음

```java
create table t1(
	column_name column_type default_value is_null,
	..
	,
	..  
	);
```

- 데이터 타입은 처음 보는 것이 많은데,.. 나중에 기회되면 정리할 것! (NUMBER, NVARCHAR2, CLOB,  ... )

<br>

## 데이터 넣기

```java
INSERT INTO t1 VALUES (...);
```