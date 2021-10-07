## View와 Controller의 분리

View와 Controller의 역할을 분리하면서 우리는 Controller를 통해 View에 접근하게 되었다. 

⇒ 즉 사용자가 View에 직접 접근할 수 없게 해야한다!

<br>

### 사용자가 접근할 수 없는 위치

⇒ WEB-INF (직접 접근할 수 없는 비공개 위치 → Controller를 통해서만 접근 가능하다)

<br>

### 서버에서 요청하는 view의 위치

`/WEB-INF/view/index.jsp` : 어플리케이션의 루트(webapps) 아래의 WEB-INF → 절대 경로

<br>

### dispatcher에서 url-mapping

- root 부터 써야함!
- `/index`

<br>

## Context 변경하기

- 여러 개의 프로젝트가 있을 때 url 을 구분해주기 위함 → 우리는 하나의 프로젝트만 있기 때문에 root url을 사용할 것임!
- 프로젝트 > 속성 > web project settings > `/`로 변경
- Servers 탭에서 현재 실행중인 프로젝트 모두 삭제 후 재실행

<br>

## 반복되는 View 파일 경로 단축하기

- Controller에서 View를 요청할때 반복해서 나오는 내용 줄이기 위해
    
    ⇒ **ViewResolver** 사용하기!
    

```xml
<bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
		<property name="prefix" value=""></property>
		<property name="suffix" value=".jsp"></property>
</bean>
```