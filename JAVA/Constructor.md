## 생성자

- 클래스에서 어떤 생성자도 정의하지 않았을 때 기본 생성자가 컴파일러에 의해 자동 생성된다.
- 하나의 생성자라도 정의하였다면 기본 생성자는 만들어지지 않는다.
- 생성자는 overloading이 가능하다.

<br>

## 상속과 생성자

- 아래 코드의 Child 클래스에는 `public Child(){super();}`이 생략되어 있다.

    ```java
    class Parent{
        public Parent(){}
    }
    ```

    ```java
    class Child{}
    ```

- 부모 클래스에 기본 생성자가 정의되어 있지 않은 경우 자식 클래스는 부모 클래스의 생성자 중 하나의 형태와 같은 생성자를 정의해야 한다.

    ```java
    class Parent{
        public Parent(String s){} //기본 생성자 정의 안 됨
        public Parent(int i){}
    }
    ```

    ```java
    class Child{
        //정의 안하면 에러
        //기본 생성자에서 기본 super 생성자를 호출하기 때문
        public Child(String s){super(s);}
    }
    ```

-  자식 클래스의 모든 생성자는 `super();`가 **최상단의 위치**에 생략되어 있다.