
## Block

- User mode에서 실행 중이던 프로세스가 Kernal  도움을 받아야 할 때 시스템 콜을 이용하여 Kernal mode를 실행하게 된다
- 예를 들면 I/O 작업 같은
- 이때 application(user) 단의 스레드에는 I/O 작업이 끝나기 전까지 block이 걸리게 된다
- I/O 작업이 종료되고 데이터가 반환되었을 때 block이 풀리게 된다.
- **결국 application단은 kernal mode 동안 아무런 동작도 안하는 것처럼 보이게 된다**
    
    ⇒ CPU 낭비가 발생한다
    

**⇒ 제어권이 호출된 함수에게 넘어갔다 결과값과 함께 제어권이 호출한 함수에 돌아오는 경우**

## Non-Block

- Blocking과 다르게 Nonblocking은 kernal mode 중에도 application(user) 단의 작업을 중단시키지 않는다.
- 이는 I/O 작업 요청하고 **바로 kernal 에서 바로 데이터를 반환**받았기 때문이다.
- 이때 반환 받는 데이터는 그 순간 가져올 수 있는 데이터이다.
- 따라서 application은 원하는 데이터를 모두 가져올 때까지 **반복적인 요청**을 보내게 된다
    
    ⇒ 이러한 요청을 **polling** 이라고 한다
    
- 만약 pooling이 수많은 클라이언트에 의해 동시다발적으로 발생하면 cpu에 부담이 될 수 있다.

**⇒ 제어권은 호출된 함수에서 바로 반환되게 된다(호출된 함수는 다른 쓰레드로 실행되든지 뭐.. ), 결과값을 가져오기 위해 polling을 반복적으로 요청**

## Synchronous

- user mode에서 요청한 system call이 완료될 때까지 기다리고 결과물을 가져온다
- 즉 제어권과 반환됨과 동시에 결과값이 반환된다

**⇒ 제어권과 결과값의 반환 시점이 동일하다**

## Asynchronous

- system call의 완료를 기다리지 않고 나중에 완료가 되면 그 때 결과물을 받아온다
- system call 완료되었을 때 **interrupt 발생**

**⇒ 제어권의 반환과 결과값의 반환 시점이 동일하지 않다**

  

## 그렇다면 Block/Non-block과 동기/비동기의 차이는?

**⇒ 두 용어는 관심사(관점)가 다르다!**

### Block과 NonBlock: 제어권을 누가 갖는가에 대한 관심을 가짐

- **호출되는 함수가 바로 리턴하느냐 마느냐**가 관심사
- 바로 리턴 = **제어권을 호출하는 함수가 갖게 됨** ⇒ NonBlocking
- 작업을 마칠 때까지 **호출된 함수가 제어권을 가짐** = 데이터가 모두 모였을 때 리턴 ⇒ Blocking

### 동기와 비동기: 제어권을 반환하는 시간, 타이밍에 대한 관심

- **호출되는 함수의 작업 완료 여부를 누가 신경쓰느냐**가 관심사
- 호출되는 함수의 작업 완료를 **호출한 함수**가 신경쓰면 **Synchronous**
    
    > 호출하는 함수가 호출되는 함수의 작업 완료 후 리턴을 기다리거나, 또는 호출되는 함수로부터 바로 리턴 받더라도 작업 완료 여부를 호출하는 함수 스스로 계속 확인하며 신경쓰면 Synchronous다.
    
- 호출되는 함수의 작업 완료를 **호출된 함수**가 신경쓰면 **Asynchronous**
    
    > 호출되는 함수에게 callback을 전달해서, 호출되는 함수의 작업이 완료되면 호출되는 함수가 전달받은 callback을 실행하고, 호출하는 함수는 작업 완료 여부를 신경쓰지 않으면 Asynchronous다.


## Synchronous & Non-block

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/75a52e81-f02b-4bd5-980a-056e0c87e1ff/Untitled.png)

- Synchronous: 제어권 반환 시점과 결과 전달 시점이 동일하다
- Non-block: 제어권이 바로 호출된 함수에게 전달된다
- 위의 그림을 보면 호출하자마자 kernal은 EAGAIN(완료되지 않음)을 결과값으로 하여 제어권과 결과를 반환하고 있다. 따라서 **동기이면서 논블록!**
- 예시로는 `자바의 future.isDone()`가 있다
    
    ```java
    Future ft = asyncFileChannel.read(~~~);
    
    while(!ft.isDone()) {
        // isDone()은 asyncChannle.read() 작업이 완료되지 않았다면 false를 바로 리턴해준다.
        // isDone()은 물어보면 대답을 해줄 뿐 작업 완료를 스스로 신경쓰지 않고,
        //     isDone()을 호출하는 쪽에서 계속 isDone()을 호출하면서 작업 완료를 신경쓴다.
        // asyncChannle.read()이 완료되지 않아도 여기에서 다른 작업 수행 가능 
    }
    
    // 작업이 완료되면 작업 결과에 따른 다른 작업 처리
    ```
    

## Asynchronous & block

- 제어권이 호출된 함수에 있기 때문에 호출한 함수가 비동기 실행을 하더라도 할 수 있는게 없음 즉 synchronous & block과 거의 비슷한 성능
- 따라서 이 조합을 의도해서 사용하는 경우는 없고, **의도하지 않게 이 조합이 되지 않도록 주의해 주어야 한다.**
- 대표적인 케이스는 **Node.js와 MySQL**의 조합 (*이 조합으로 졸프했는데 ㅎ..*)
    
    > Node.js 쪽에서 callback 지옥을 헤치면서 Async로 전진해와도, 결국 DB 작업 호출 시에는 MySQL에서 제공하는 드라이버를 호출하게 되는데, 이 드라이버가 Blocking 방식이라고 한다.
    > 

## Block VS Synchronous

- 시스템의 반환을 기다린다는 측면에서 공통점이 있음
- **Blocking**: kernal mode의 반환을 기다리는 동안 waiting queue에 머무는 것이 필수
- **Synchronous**: kernal mode의 반환을 기다리는 동안 waiting queue에 머무는 것이 필수가 아님
    

## Reference

- [https://simsim231.tistory.com/132](https://simsim231.tistory.com/132)
- [https://homoefficio.github.io/2017/02/19/Blocking-NonBlocking-Synchronous-Asynchronous/](https://homoefficio.github.io/2017/02/19/Blocking-NonBlocking-Synchronous-Asynchronous/)
- [https://nesoy.github.io/articles/2017-01/Synchronized](https://nesoy.github.io/articles/2017-01/Synchronized)
- [https://snoop-study.tistory.com/85](https://snoop-study.tistory.com/85)
- [https://velog.io/@codemcd/Sync-VS-Async-Blocking-VS-Non-Blocking-sak6d01fhx](https://velog.io/@codemcd/Sync-VS-Async-Blocking-VS-Non-Blocking-sak6d01fhx)
