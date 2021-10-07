## ApplicationContext 이용하기

: 작성한 지시서를 읽기위한 인터페이스

- ClassPathXmlApplicationContext: 어플리케이션의 루트부터 경로를 사용할 때 → 가장 보편적이고 합리적
- FileSystemXmlApplicationContext: 현재 파일 시스템의 경로를 사용할 때
- XmlWebApplicationContext: 웹의 url을 사용할 때
- AnnotationConfigApplicationContext: 어노테이션을 이용할 때

```java
ApplicationContext context = 
				new ClassPathXmlApplicationContext("spring/di/setting.xml");
```

- ApplicationContext 이용하기 위해, maven 프로젝트로 변경 후 spring context 라이브러리 다운로드 받아야 함

<br>

## 지시서의 객체 사용하기

1. 생성한 객체명 이용하기

    ```java
    ExamConsole console = (ExamConsole) context.getBean("console");
    ```

    - getBean([객체이름]): 반환값은 Object이기 때문에 형변환이 필요
2. 자료형 이용하기

    ```java
    ExamConsole console = context.getBean(ExamConsole.class);
    ```

    - 패키지까지 작성할 필요 없음
    - 형변환이 필요 없어 객체를 가져오는 것이 더 깔끔하기 때문에 더 선호되는 방법