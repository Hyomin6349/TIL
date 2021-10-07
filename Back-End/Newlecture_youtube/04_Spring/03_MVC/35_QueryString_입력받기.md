## Request 이용하기

- Spring MVC에서 제공하는 Front Controller
- Front Controller에서 request, response 이용할 수 있도록 해줌
- 필요시에 변수를 선언하여 사용 (HttpServletRequest)
- **쿼리문의 key 값의 이름을 선언하면 바로 값을 얻어올 수 있음**
    
    ```java
    public void list(String p){}
    ```
    
- 다른 이름으로 쿼리 값 가져오기 (page 이름으로 p 값 이용하기)
    
    ```java
    public void list(@RequestParam(p) String page){}
    ```
    
- @**RequestParam** 속성 이용하기
    - name: 요청하는 변수명
    - defaultValue: 초기값
    - required: 요청하는 변수 값이 없어도 되는가? boolean 값
    - value: name과 같은 속성
