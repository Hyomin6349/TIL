Cookie의 maxAge 옵션을 설정해주지 않으면 브라우저의 생명주기와 동일하게 유지된다

→ 브라우저가 닫히면 Cookie가 사라짐

<br>

maxAge 옵션으로  Cookie의 **만료 시간(날짜)**을 설정할 수 있다.

```java
valueCookie.setMaxAge(60*60); //60분 동안 유지
```