## 독립적 프로세스

- 원칙적으로 프로세스는 독립적임
- 하나의 프로세스가 다른 프로세스 수행에 영향을 미치지 않는다

<br>

## 협력 프로세스

- 프로세스가 다른 프로세스의 수행에 영향을 미치는 경우

<br>

## IPC (프로세스 간 협력 매커니즘)

- **message passing:** 커널을 통해 메시지 전달
    - 공유 변수를 사용하지 않고 통신
    - Direct Communication: 통신하려는 프로세스 이름을 명시적으로 표시
    - Indirect Communication: mailbox 또는 port를 통해 메시지 **간접 전달**
- **shared memory:** 서로 다른 프로세스가 메모리를 공유
