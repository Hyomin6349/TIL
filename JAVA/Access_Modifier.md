- **public**: 모든 대상, 다른 패키지의 class에 접근하는 경우 import한 후 사용하면 된다.
- **protected**: 같은 패캐지 내에 있는 클래스만 접근하지만, 상속 관계에 있는 클래스라면, 즉 자식 클래스라면 접근 가능하다.

    test1.java

    ```java
    package p1;
    import p2.test2;
    public class test1 extends test2 {
        void method(){
            test1 t1 = new test1();
            t1.i = 10;
        }
    }
    ```

    test2.java

    ```java
    package p2;
    public class test2{
        protected int i;
    }
    ```

- **default**: 보통 생략된 형태로 많이 쓰임. 다른 패키지 내에 있는 클래스만 접근 가능
- **private**: 같은 클래스에서만 접근 가능
- public > protected > default > private
- public과 default만 클래스의 접근 제한자로 사용할 수 있음