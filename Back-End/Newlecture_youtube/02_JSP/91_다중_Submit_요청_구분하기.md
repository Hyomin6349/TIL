## 하나의 Form 태그에 Submit 버튼이 여러개 일 때

- name 속성을 이용하여 파라미터를 받기
- value 속성으로 submit 버튼 분류

```java
String cmd = req.getParameter("cmd");
		
	switch(cmd) {
	case "일괄공개":
		break;
	case "일괄삭제":
		break;
	}
```