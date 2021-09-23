## Component 어노테이션

- 클래스명 위에 Component 어노테이션을 붙여주면 객체를 생성해준다
- context를 통해 annotation-config 설정을 해주었는데 이는 설정 파일에서 객체를 생성할 때 annotation을 확인하는 것
- Component 같은 경우는 annotation을 사용하여 객체를 생성하는 경우로 별도의 설정을 해주어야 한다
- `<context:component-scan base-package="spring.di.ui">` : spring.di.ui 패키지 안에 component 어노테이션이 붙은 클래스를 찾아 객체를 생성해라
- component-scan 설정은 annotation-config 설정을 포함하기 때문에 annotation-config 설정을 지워주어도 Autowired가 정상 작동한다.
- `@Component("i[d]")`를 이용하여 id 값을 지정한다
- 여러개의 패키지에서 component를 검색하고 싶을 때 쉼표를 사용하여 여러 개의 패키지를 포함한다.

<br>

## 초기값 설정하기

- **value 어노테이션** 이용
- 초기값을 설정해주고 싶은 필드마다 value 어노테이션을 붙여준다.

```java
@Component("exam2")
public class NewlecExam implements Exam { 
	
	@Value("20")
	private int kor;
	@Value("30")
	private int eng;
	@Value("70")
	private int math;
	@Value("80")
	private int com;
}
```

<br>

## MVC 모델에 적합하지 않은 Component 어노테이션

- 우리가 사용하는 클래스 중에는 소스 코드를 수정할 수 없는 클래스들도 있다 (예를 들어 자바에서 제공하는 클래스)
- 이러한 클래스 객체를 만들 때는 Conponent 어노테이션을 사용할 수 없다
- 그렇다면 xml을 이용한 객체 생성 방식과 어노테이션을 이용한 객체 생성 방식을 혼합하여 사용해야 하는가?
- 아니다!! 설정 방법은 하나로 통일하는 것이 적합하다. 
- 그렇다면, annotation으로는 어떻게 객체를 생성해야 하는가?