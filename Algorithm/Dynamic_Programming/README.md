## 동적계획법

: 작은 부분 문제들의 해를 구하고 이를 이용하여 큰 크기의 부분 문제를 해결하는 알고리즘 설계 기법

- 그리디 알고리즘과 같이 **최적화 문제**를 해결하는 알고리즘
- 최대, 최소 + 경우의 수 구하는 문제

<br>

### 최적 부분문제 구조

- 모든 최적화 문제가 DP로 해결가능한 것은 아님 ⇒ **최적화의 원칙**을 만족해야 함
- 최적화의 원칙: 어떤 문제에 대한 해가 최적일 때 그 해를 구성하는 **작은 문제들의 해 역시 최적이어야 함**

### 중복 부분문제 구조

- 부분 문제들이 중복해서 나오는 경우
- 다시 해를 구할 필요 없이 메모이제이션을 이용

### 분할 정복과의 비교

- 동적 계획법은 부분 문제간의 연관이 있어 **재귀적으로 해결**한다

    → 부분 문제들은 더 작은 부분 문제를 공유, 의존적 관계 존재

    → 모든 부분 문제의 결과를 저장하고 재사용

- 분할 정복은 **연관 없는 부분 문제로 분할**하여, 부분 문제를 재귀적으로 해결한 **결과를 결합**하는 방식