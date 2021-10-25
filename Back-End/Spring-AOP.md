## AOP (Aspect Oriented Programming)

: 핵심 관심 사항과 **공통 관심 사항**

- 공통 관심 사항을 적용하기 위한 중복 코드를 한데로 모아 처리하는 것
- 사용 예
    - 간단한 메서드 성능 수행
    - 트랜잭션
    - 예외 반환
    - 로깅, 인증, 권한
- 용어
    - Target: 핵심 기능을 담고 있는 모듈, 부가 기능을 부여할 대상
    - Advice: **어느 시점**에 어떤 Aspect(공통 관심 기능)을 적용할지 정의한 것, Target에 제공할 부가 기능을 담고 있는 모듈
    - JoinPoint: Aspect가 적용 될 수 있는 시점, 거의 모든 메서드
    - PoingCut: advice 메서드가 적용될 target 메서드를 필터링하는 것, 정규표현식으로 지정
    