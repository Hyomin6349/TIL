## Docker

- 애플리케이션을 신속하게 **구축, 테스트 및 배포**할 수 있는 **소프트웨어 가상화 플랫폼**
- **컨테이너** 단위로 패키징
- 컨테이너에는 라이브러리, 시스템 도구, 코드, 런타임 등 실행에 필요한 모든 것이 포함
- 컨테이너는 **OS레벨의 가상화**
- Docker Image: 컨테이너를 실행할 수 있는 실행 파일, 설정 값 등
    
    ⇒ Docker Image를 컨테이너에 담아 사용한다
    
- Git hub와 동일한 기능을 지원하는 Docker hub가 있다 (image를 올리고 다운받고)

<br>

### 장점

- **성능 향상, 이식성 쉬운 Scale Out**
- 가상화 → 안정성을 높이고 리소스도 최대한 활용할 수 있는 것
- 기존의 OS 가상화 방식은 Host OS 위에 Guest OS 를 두면서 무겁고 느리지만 컨테이너 가상화는 Host의 커널을 공유하여 **Host OS가 사용하는 자원을 분리하여 여러 환경을 만들 수 있도록 한 것**

<br>

### 단점

- Host OS 가상화보다 보안성이 떨어진다
- OS 가상화의 커널을 공유하지 않음

[[Docker] Docker의 개념 및 핵심 설명](https://khj93.tistory.com/entry/Docker-Docker-%EA%B0%9C%EB%85%90)