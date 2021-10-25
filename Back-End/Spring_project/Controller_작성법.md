```java
@RestController
@RequestMapping("/users")
public class UserController {
	
	@Autowired
	private UserService userService;
	
	@PostMapping
	public Message SignUp (@RequestBody UserDto user){
		System.out.println(user.toString());
		
		Message message = new Message();
		
		try {
			userService.insert(user);
		} catch (SQLException e) {
			e.printStackTrace();
			message.setCode(e.getErrorCode());
			message.setMessage(e.getMessage());
			return message;
		}
		
		message.setCode(0);
		message.setMessage("request success");
		message.setData(user);
		
		return message;
	}
}
```

## RestController

- Controller와 다른 점은 모든 메서드에 자동으로 @ResponseBody 어노테이션을 추가해준다는 점
- 원래 MVC 패턴 공부할 때는 view를 반환하면서 viewResolver를 통해서 jsp 페이지를 반환했는데, API로 controller를 만들다 보니 json 객체를 반환하는 경우만 있어서 RestController 사용함

## Message

- 내가 정한 반환 형식
- code, message, data를 포함한다.
- 각 필드에 getter, setter가 있어야 response로 넘어갈 수있다.

## RequestBody

- 자동으로 request 들어온 것으로 객체 초기화
- 들어오지 않은 값은 null 값으로 초기화
- 클라이언트에서 보내주는 변수 명과 객체의 필드명을 통일해야 한다.

## ResponseEntity

- HttpEntity를 상속받은 클래스로 HttpRequest에 대한 응답 데이터를 보내기 위한 객체
- HttpStatus, HttpHeaders, HttpBody를 포함
- ResponseBody와 다른점은 Response header를 직접 커스텀(?)할 수 있다는 점