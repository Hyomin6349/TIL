jQuery 선택자를 통해 반환된 DOM 객체(래퍼세트)들을 처리하는 다양한 메서드

- `size()`: 반환 객체 개수
- `get(index)` → HTML 객체 반환
- `index(element)`
- `add(element)`: 래퍼세트에 요소 추가
- `not(element)`: 래퍼세트에 요소 삭제
- **`each(function(index, element){})`:** 반환된 요소들에 대해 반복문 수행

    ```jsx
    $('h2').each(function(index, item){
    	...
    })
    ```

- `filter(selector) or filter(function(index, element){})` : selector로 하거나 function의 index를 이용하여 래퍼세트를 필터링
    - `end()` 메서드를 이용하면 index 초기화 되지 않고 사용 가능 (?)
    - 반환된 래퍼세트를 필터링
- `eq(index)`: index에 해당하는 객체를 새로운 래퍼세트로 하여 반환
- `find(selector)` : 래퍼세트 요소들의 **하위 자손**을 탐색하기 위해 사용 → 보통 id 나 class 명을 selector로 많이 사용

    > find 는 전체(혹은 기준 값 하위)에서 검색을 하지만 filter 는 자기 자신의 레벨에서 검색을 한다.
    출처: [https://ghost41m.tistory.com/entry/jQuery-find-와-filter-의-차이점](https://ghost41m.tistory.com/entry/jQuery-find-%EC%99%80-filter-%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90)

<br>

### 속성 제어 메서드

- `attr(name)` : 래퍼세트의 첫번째 요소에 대한 속성 값을 **반환** → 해당 속성 없다면 undefined 반환
- `attr(name, value)` : 모든 래퍼세트에 같은 속성 값 **설정**
- `attr(name, function(index, attr){})` : 규칙이 있을 때 function 이용해서 속성 값 **설정**
- `attr(object)` : 단순하게 값을 넣을 때 사용
- `html()` : 인자가 없으면 하위 html 반환, 인자 있으면 innerHtml과 동일
- `text()` : 하위에 존재하는 text 요소 반환, 인자 있으면 text 넣기