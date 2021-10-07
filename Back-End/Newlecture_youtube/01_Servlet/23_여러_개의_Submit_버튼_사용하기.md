## 여러 개의 submit 버튼 어떻게 구별할까?

```xml
<input type="submit" value="덧셈"/>
<input type="submit" value="뺄셈"/>
```

- submit 버튼을 눌렀을 때 크롬의 개발자 도구 네트워크 탭에서 보면 데이터만 전송되는 것을 확인할 수 있다

    ⇒ Form data에 값만 출력됨

- input 태그에 name 값을 넣음으로써 값을 전달할 수 있다

    ```xml
    <input type="submit" name="operator" value="덧셈"/>
    <input type="submit" name="operator" value="뺄셈"/>
    ```

    ⇒ operator 값은 덧셈 혹은 뺄셈이라는 정보를 추가!