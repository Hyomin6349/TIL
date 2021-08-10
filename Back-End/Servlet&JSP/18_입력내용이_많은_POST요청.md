- 사용자의 요청을 모두 url에 노출시키는 것이 바람직하지 않는 경우가 있다
    1. 요청이 매우 긴 경우 → url은 길이 제한이 있다
    2. 중요한 정보인 경우
- POST method를 이용한다
- POST 요청은 url에 정보를 넣는 것이 아닌 문서 요청 바디안에 정보를 담아서 보내는 것

```html
<form action="/notice-reg" method="post">
		<div>
				<label>제목: </label><input type="text" name="title"/>
		</div>
		<div>
				<label>제목: </label>
				<textarea name="content"></textarea>
		</div>
		<div>
				<input type="submit" value="등록"/>
		</div>
</form>
```

- 하지만! 한글을 담는 경우 문서가 깨지는 경우가 발생하는데!!