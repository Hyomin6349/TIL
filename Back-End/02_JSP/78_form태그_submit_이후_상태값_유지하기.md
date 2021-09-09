## param을 이용하여 상태값 유지하기

검색칸에 검색어 입력 후, 검색 버튼을 누르면 url이 수정되고 새로운 화면이 나오면서 검색칸에 있던 내용이 사라진다. 이 내용을 유지하고 싶다!

⇒ 결국 검색칸의 값은 url에 넘겨진 값과 동일

⇒ param 변수를 이용해서 값을 가져오자

```html
<form class="table-form">
	<fieldset>
		<legend class="hidden">공지사항 검색 필드</legend>
		<label class="hidden">검색분류</label>
		<select name="f">
			<option ${(param.f == "title")?"selected":""} selected value="title">제목</option>
			<option ${(param.f == "writer_id")?"selected":""} value="writer_id">작성자</option>
		</select> 
		<label class="hidden">검색어</label>
		<input type="text" name="q" value="${param.q}"/>
		<input class="btn btn-search" type="submit" value="검색" />
	</fieldset>
</form>
```

- 검색어가 들어가는 input 태그의 **value**에 **EL 표기법**을 이용하여 param.q 값을 넣어준다
- **삼항연산자**를 이용해서 selected 속성을 넣어주거나 빼준다

    → 신기한게, string 비교인데 **== 연산자**를 사용한 비교가 가능하다

    → eq를 사용해도 된다 `${(param.f eq "title")?"selected":""`