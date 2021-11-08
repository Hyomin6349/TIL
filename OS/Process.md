## 프로세스의 문맥(context)

: 현재 시점의 프로세스 정보를 알기 위한 정보

- CPU의 수행 상태를 알기위한 **Program Counter**, 각종 **Register**
- 프로세스의 주소 공간: code, data, stack
- 프로세스 관련 커널 자료 구조: PCB, Kernal stack
    
    → kernal은 프로세스가 할 수 없는 일을 운영체제가 해주는 것(System call)
    
    → **프로세스마다 별도의 커널 스택 영역**을 가진다 
    
<br>

## 프로세스의 상태

- **Running**: CPU를 잡고 실행 중인 상태
- **Ready**: CPU를 기다리는 상태 (cpu만 얻으면 바로 실행할 수 있는 상태)
- **Blocked(wait, sleep)**: CPU를 얻어도 instruction 수행 할 수 없는 상태
    - I/O 요청이 만족되지 않은 상태
    - 디스크에서 file을 읽어와야 하는 경우
- Suspended(stopped): 외부적인 이유로 프로세스의 수행이 정지된 상태
- New: 프로세스가 생성 중인 상태
- Terminated: 수행이 끝난 상태 (끝나고 정리 중인 상태)

<br>

## PCB

: 운영체제가 각 프로세스를 관리하기 위해 프로세스당 유지하는 정보

- 프로세스 상태, id
- 스케쥴링 정보, 우선순위
- cpu 수행 관련 하드웨어 값: pc register

<br>

## Context Switch

: 한 프로세스에서 다른 프로세스로 넘겨주는 과정

- 사용자 프로세스(User mode)를 실행하다 운영체제(kernal, monitor mode)에 권한이 넘어가는 경우는 문맥 교환이 아니다
- 보통 timer interrupt, I/O 요청 system call이 context swtich의 원인이 된다

<br>

## Scheduler

- **Long-Term scheduler (job scheduler)**
    - New 상태의 프로세스 중에서 어떤 것들을 **ready queue**로 보낼지 결정
    - 프로세스에 **memory**를 주는 문제
    - degree of Multiprogramming을 제어 (프로세스의 개수 제어)
        
        → 메모리에 올라가있는 프로세스의 수를 제어
        
        → 메모리에 너무 많거나, 적으면 프로그램의 성능이 좋지 않다
        
    - time sharing system에는 보통 장기 스케줄러가 없음
        
        → 무조건 ready 상태가 됨
        
- **Short-term scheduler**
    - 어떤 프로세스를 다음번에 running 시킬지 결정
    - 프로세스에 CPU를 주는 문제
- **Medium-term scheduler (swapper)**
    - 메모리에 너무 많은 프로세스가 있을 때 메모리에서 디스크로 쫒아내는 역할