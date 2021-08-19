## Context

: 사이트의 볼륨이 커지면서 Root에 여러 디렉토리가 추가된 상황에 분업을 위해 **별개의 사이트로 나누어 개발하되 Context는 유지**한다 ⇒ **주소체계는 동일**하게

예) 네이버의 뉴스, 웹툰, 부동산은 각자 별개의 사이트로 나누어 제작하지만, Naver라는 Context는 동일하게 유지한다.

⇒ 물리적으론 별개의 사이트 하지만 같은 Context를 유지하면서 **하위 디렉토리에서 돌아가는** **것 처럼**보임. (Context를 다른 말로 가상 경로라고도 함)

<br/>

1. ROOT>it>news.txt 로 관리하던 it의 볼륨이 커진경우
2. ROOT 하위 디렉토리에 존재하던 it를 다른 위치로 이동시킨다 
3. [localhost:8080/it/news.txt는](http://localhost:8080/it/news.txt는) 이제 404에러가 발생한다
4. 톰캣>conf>server.xml에 Context를 추가한다.

```xml
<Context path="it" docBase="C:\apache-tomcat-10.0.5\webapps\ITWeb" privileged="true"/>
```

- path: 사용할 가상 경로
- docBase: 서비스할 디렉토리의 위치
1. 서버를 재시작하여 테스트한다.
2. [localhost:8080/it/news.txt](http://localhost:8080/it/news.txt) 잘 동작!

<br/>

하지만, 톰캣 버전이 올라갈 수록 context를 server.xml에 지저하는 것은 지양하고 있다...

서버를 재시작해야 하기 때문..