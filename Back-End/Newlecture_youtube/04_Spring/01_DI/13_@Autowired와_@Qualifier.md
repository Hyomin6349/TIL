## @Autowired 어노테이션

객체를 생성할 때 setter 메서드에 Autowired 어노테이션이 붙어있다면 자동으로 객체끼리 바인딩을 진행해준다

> 객체를 생성할 때 Annotation을 확인하도록 하는 설정을 추가해 주어야 한다. namespace에서 context를 추가한 뒤 context:annotation-config 태그를 추가함으로써 객체를 생성할 때 annotation 설정을 같이 해주는 것을 포함하자!

### 어떻게 바인딩을 수행하나?

필요한 객체 **클래스**가 무엇인지를 확인하고 IoC 컨테이너 내부에서 일치하는 클래스 객체를 찾아 바인딩 해준다.

### 일치하는 클래스 객체가 여러 개라면?

- setter에 사용된 변수명과 일치하는 id를 가진 객체가 있다면 그 객체와 바인딩해준다.
- **Qualifier 어노테이션**을 사용한다. `@Qualifier("exam1")` : exam1 id값을 가진 객체와 바인딩

<변경 전>

```xml
<bean id="console" class="spring.di.ui.InlineExamConsole">
	<property name="exam" ref="exam"></property>
</bean>
```

<변경 후>

```java
@Autowired
@Qualifier("exam2")
@Override
public void setExam(Exam exam) {
	this.exam = exam;
}
```

<br>

## Autowired의 위치

1. 필드 앞에
    - 기본 생성자가 호출하면서 DI
    - 기본 생성자가 없다면 에러 발생
2. 생성자 앞에
    - Qualifier은 파라미터 앞에 넣어줘야 한다
    - 여러 개의 파라미터가 주어질 수 있기 때문

    ```java
    @Autowired
    public InlineExamConsole(@Qualifier("exam2") Exam exam) {
    		this.exam = exam;
    	}
    ```
 
3. setter 메서드 앞에

    ```java
    @Autowired
    @Qualifier("exam2")
    @Override
    public void setExam(Exam exam) {
    	this.exam = exam;
    }
    ```

<br>

## Autowired의 required 옵션

- Autowired는 required 옵션을 가지고 있다
- 기본적으로 true 값으로 바인딩해줄 객체가 없으면 에러발생
- false 값으로 변경하면 바인딩할 객체가 없으면 null이 들어간다