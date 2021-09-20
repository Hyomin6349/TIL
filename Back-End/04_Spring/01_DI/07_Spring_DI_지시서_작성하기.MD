```java
Exam exam = new NewlecExam();
ExamConsole console = new GridExamConsole();
		
console.setExam(exam);
```

이 코드를 Spring의 DI 지시서로 작성해보자

- **bean 태그**를 이용하여 객체를 생성한다

    ```xml
    <bean id="exam" class="spring.di.entity.NewlecExam"></bean>
    ```

    - `Exam exam = new NewlecExam();`
    - class는 패키지 명을 포함하여 작성한다
    - id: 생성한 객체 명
- **DI**: 생성한 객체 bean에 property를 사용하여 setting 한다

    ```xml
    <bean id="console" class="spring.di.ui.GridExamConsole">
    	<property name="exam" ref="exam"></property>
    </bean>
    ```

    - property의  name속성 값은 set 함수와 매핑된다.

    ⇒ exam → setExam()

    ⇒ name → setName()

    - 따라서 해당하는 set 함수가 해당 클래스에 없으면 에러 난다
    - set 함수에 넘겨주는 객체는 value 혹은 ref 속성을 이용한다
    - value 타입 객체 혹은 reference 객체에 따라 속성을 사용한다