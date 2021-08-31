## DOM (Document Object Model)

문서 요소 집합을 트리 형태의 계층 구조로 HTML을 표현

- HTML 계층의 ROOT 노드는 document
- 아래로 **태그**나 **요소**를 표현하는 노드와 문자열이 있음

<br>

## 문서 객체 만들기

1. createElement(tagName): element node 생성
2. createTextNode(text): text node 생성
3. appendChild(node): element node에 text node를 child로 추가

```jsx
var title = document.createElement('h2');
var msg = document.createTextNode('hello');
title.appendChild(msg);
```
<br>

### 객체의 속성 설정

- 직접 설정 → 웹 브라우저에서 지원하는 태그들만 가능! 직접 정의한 객체의 속성 값을 변경할 수 없음

    ```jsx
    vat profile = document.createElement('img');
    profile.src = 'profile.png';
    ```

- 메서드 이용 → 직접 정의한 객체의 속성 값도 변경 가능
    - setAttribute(name, value): name 속성명, value 속성값
    - getAttribute(name): name 속성 값을 가져옴

<br>

### inner

- innerHTML: 문자열을 HTML 태그로 삽입 → `<h2>hello</h2>` 태그 인식됨
- innerText: 문자열을 text node로 삽입

<br>

### 객체 삭제

- removeChild(childnode): 객체의 자식 노드를 제거

    ```jsx
    document.body.removeChild(childnode);
    ```

<br>

## 문서 객체 가져오기

- getElementById(id): id 값을 이용하여 element 가져오기 → id 값은 유일 값 **element**
- getElementsByClassName(className): class에 해당하는 element 배열 가져오기
- getElementsByTagName(tagname)
- getElementsByName(name): 태그의 name 속성이 name과 일치하는 element 배열
- querySelector(selector): selector에 일치하는 **첫번째 element 객체**

    **→** id로 얻어오는 경우 많이 사용

- querySelectorAll(selector): selector에 일치하는 **모든 element 배열**