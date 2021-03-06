일반 선택자

- 전체 선택자 `*{ }`
- 타입 선택자 `h1, h2, h3 { }`
- 클래스 선택자 `.className{ }`
- ID 선택자로 분류 `#idName{ }`

복합 선택자

- 자식 선택자 `E1 > E2 { }`
- 하위 선택자 `E1 E2 { }`
- 인접 형제 선택자 `E1 + E2 { }`
- 일반 형제 선택자 `E1 ~ E2 { }`

이외에도

- 가상 클래스 선택자 `가상클래스 { }`
- 가상 엘리먼트 선택자 `::가상 엘리먼트 { }`
- 속성 선택자

<br>

### 전체 선택자

글꼴 설정이나 여백을 지정할 때 많이 씀

### 선택자의 우선 순위

전체 선택자 < 타입 선택자 < 클래스 선택자 < ID 선택자

⇒ 선택 범위가 디테일할 수록 우선 순위가 높다!

### 타입 선택자

엘리먼트의 이름을 직접적으로 선택할 수 있음 = 태그명을 사용!

### 자식 선택자와 하위 선택자

- 자식 선택자는 직속 하위 엘리먼트만 적용 = 1단계 하위 → 더 많이 사용함!
- 하위 선택자는 모든 하위 엘리먼트에 적용

### 인접 형제 선택자와 일반 형제 선택자

- 인접 형제 선택자: 바로 아래에 존재하는 형제 엘리먼트 한 개에 적용
- 일반 형제 선택자: 형제 관계를 이루는 엘리먼트들에 적용

### 가상 클래스 선택자

- :link
- :visited
- :hover

등.. 상황에 따라서 다른 css 를 주고 싶을 때

`a:visited { }` : 링크에 접속했을 때

### 속성 선택자

- [A] : A 속성을 가진 모든 엘리먼트
- [A=V]: A의 속성 값이 V와 일치하는 모든 엘리먼트
- [A~=V]: 속성값이 V를 포함하는 모든 엘리먼트
- 등등

### CSS 규칙 적용 우선 순위

- 같은 엘리먼트에 두 개 이상의 css가 적용된다면 ⇒ 마지막 규칙, 구체적인 규칙, !important가 우선 적용
- 더 구체적으로 작성된 규칙이 우선 순위를 가진다