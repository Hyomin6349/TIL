## Annotation 지시서 만들기

<기존 xml 파일>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
	<context:component-scan base-package="spring.di.ui, spring.di.entity"/>
	<bean id="exam1" class="spring.di.entity.NewlecExam" p:kor="10" p:eng="20" p:math="30" p:com="40"/>
</bean>
```

<br>

<Annotation 지시서>

```java
@ComponentScan("spring.di.ui")
@Configuration
public class NewlecDIConfig {
	@Bean
	public Exam exam (){
		return new NewlecExam();
	}
}
```

- @Bean 어노테이션을 사용하여 bean 객체 생성
- exam은 생성된 객체의 id값과 동일하다

<br>

```java
ApplicationContext context = 
				new AnnotationConfigApplicationContext(NewlecDIConfig.class);
```

- 메인에서 설정 방식 변경하기
- AnnotationConfigApplicationContext 클래스를 이용하여 설정 방법 변경
- 작성한 config 클래스를 넘겨준다