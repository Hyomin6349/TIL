- All Selector:  `$("*")`  → margin, padding, 글꼴 설정 시 사용
- Element Selector: `$('element')` →태그 명 들어감
- ID Selector: `$('#idname')` → 가장 많이 사용
- Class Selector: `$('.classname')`
- Complex Selector: `$('.name.classname')` → 보통 Selector + class Selector 조합으로 많이 사용
- Multiple Selector: `$('name, name')`

<br>

### Hierarchy Selector

- `$('Parent > Child')` : 자식 객체, 직속 하위만
- `$('Ancestor Descendant')` : 하위 객체
- `$('element ~ element')` : 모든 형제
- `$('Previous + Next ')` : 인접한 형제

<br>

### Attribute Selector

- `$(selector[attr])` : attr 속성 가진 객체
- `$(selector[attr="value"])`
- `$(selector[attr!="value"])`
- `$(selector[attr~="value"])` : value 포함 값
- `$(selector[attr^="value"])` : value로 시작하는 값
- `$(selector[attr$="value"])` : value로 끝나는 값
- `$(selector[attr*="value"])` : value 포함 값

<br>

### Filter Selector

- `el:checked`
- `el:first` : 첫번째 자식
- `el:last` : 마지막 자식
- `el: even` : 짝수 자식
- `el: odd` : 홀수 자식
- `el: contains(str)` : 텍스트 str을 포함하는 요소만 선택

...