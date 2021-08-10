## 스택(Stack)

: 물건을 쌓아 올리듯 자료를 쌓아 올린 형태의 자료구조

- 선형 자료구조 → 선후 관계가 하나씩
- LIFO(Last In First Out): 마지막에 삽입한 자료를 가장 먼저 꺼낸다.
- 스택의 최상단 = 가장 마지막 원소 = top
- top에서 삽입과 삭제가 이루어진다.
- push: 원소 삽입
- pop: 원소 삭제
- peek: 원소 확인 → 가장 위 top 원소 확인

## java.util.Stack

- 주요 메서드: push(), pop(), isEmpty(), size()
- Stack<Generic type>

## 활용

**괄호 검사**

- 조건
    1. 왼쪽 괄호의 개수와 오른쪽 괄호의 개수가 같아야 한다.
    2. 같은 괄호에서 왼쪽 괄호는 오른쪽 괄호보다 먼저 나와야 한다.
    3. 괄호 사이에는 포함 관계만 존재한다.

**Function call**

프로그램에서의 함수 호출과 복귀에 따른 수행 순서를 스택 구조로 관리

**후위 표기법 계산**

1. 피연산자를 만나면 스택에 push
2. 연산자를 만나면 필요한 만큼의 피연산자를 스택에서 pop하여 연산하고, 연산 결과를 스택에 push
3. 연산이 끝나면 스택에서 연산 결과를 pop