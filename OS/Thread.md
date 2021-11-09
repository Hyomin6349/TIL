## Thread

: CPU를 실행하는 단위

- Thread의 구성: pc, register set, stack space
    
    → thread마다 별도의 영역으로 구성
    
- Thread 가 공유하는 부분
    - code section
    - data section
    - os resources
    
<br>

## Thread의 장점

- 하나의 서버 스레드가 blocked 상태인 동안에도 동일한 태스크 내의 다른 스레드가 실행되어 빠른 처리를 할 수 있다.
- 동일한 일을 수행하는 **다중 스레드가 협력**하여 높은 처리율과 성능 향상을 얻을 수 있다
- 서로 다른 프로세스에서 각 스레드를 실행하여 병렬성을 높일 수 있다.
    
    → 여러개의 cpu를 가질 수 있을 때
