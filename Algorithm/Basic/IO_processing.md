## 표준 입출력

stream: 데이터의 흐름

- System.in: 표준 입력 (→ 표준 입출력 대상 변경 System.setIn())
- System.out: 표준 출력
- System.err: 표준 에러 출력

```java
System.setIn(new FileInputStream("input.txt")); //파일로 받을 때만 추가하면 됨
Scanner sc = new Scanner(System.in);
```
<br/>

## java.util.Scanner

: 파일, 입력 스트림등에서 데이터를 읽어 구분자로 토큰화하고 다양한 타입으로 형변환하여 리턴해주는 클래스 ⇒ 입력 도우미

- Scanner(File/InputStream/String source)
- 입력 스트림을 다루는 방법을 몰라도 손쉽게 입력 처리 가능
- 데이터 형변환으로 인한 편리함 (nextInt(), nextDouble(), next(), nextLine(), ... )
- 대량의 데이터 처리 시 수행시간이 비효율적 ⇒ BufferedReader 사용하는 것이 효율적

> next(): 유효 문자열을 받기 전까지 white space는 읽지 않음 
nextLine(): white space 포함.. enter를 만나기 전까지

<br/>

## java.io.BufferedReader

- 필터 스트림 유형
- line 단위의 문자열 처리 기능 제공 ⇒ readLine()
- 대량의 데이터 처리 시 수행시간이 효율적임
- 생성자로 Reader를 받음

```java
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
//System.in: inputStream
//InputStreamReader: byte -> char 변환 (더 큰 통로로 변환)
```

- StringTokenizer과 함께 사용: 구분자를 기준으로 입력을 나눠주는 도구 (기본 구분자: /t, space)

<br/>

## java.lang.StringBuilder

- 문자열의 조작을 지원하는 클래스
- 자바에서 상수로 취급되는 문자열을 조작 시마다 새로운 문자열이 생성되는 것을 방지해줌
- append()
- toString()
- setLength(): 반복적인 내용을 제거할 때 자주 사용

    1,2,3,4, ⇒ setLength(sbb.length()-1) ⇒ 1,2,3,4