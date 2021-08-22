**사용자로부터 입력을 받을 입력폼 만들기**

```html
<div>
		<form action="/hi">
			<div>
				<label>몇번의 "안녕하세요"?</label>
			</div>
			<div>
				<input type="text" name="cnt"/>
				<input type="submit" value="출력"/>
			</div>
		</form>
	</div>
```

- \<form action="/hi"> : `~/hi` URL을 요청한다
- \<input type="text" name="cnt">: 쿼리스트링을 추가한다 `?cnt=3`