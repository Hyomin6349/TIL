## @Controller 이용하기

### 기존 코드

```java
public class IndexController implements Controller{

	@Override
	public ModelAndView handleRequest(HttpServletRequest request, HttpServletResponse response) throws Exception {
		
		ModelAndView mv = new ModelAndView("root.index");
		return mv;
	}

}
```
<br>


### Annotation 이용 코드

- 설정 파일에 `<mvc:annotation-driven>` 추가 ⇒ url mapping을 위함
- 이전의 `<context:component-scan>`은 annotation을 찾아서 객체화한 뒤 메모리에 올리는 역할

```java
@Controller
public class HomeController {
 
	@RequestMapping("/index")
	public String index() {
		return "root.index";
	}
}
```

- `@RequestMapping("/index")`: url을 기반으로 view 파일을 찾아준다 (`WEB-INF/view/index.jsp`)
- url이 매핑되는 것이 class가 아니라 **메서드** ⇒ Controller 마다 다른 클래스로 정의하는 것이 아닌 **폴더마다의 Controller class** 를 정의
- IndexController에서 HomeController로 파일명 변경 (폴더마다 class 정의)
- 원하는 View 파일명을 String 리턴 타입으로하여 반환한다
- Controller: 문서를 반환값으로 하는 Controller
- RestController: 데이터를 반환값으로 하는 Controller (ResponseBody 메서드와 동일)
