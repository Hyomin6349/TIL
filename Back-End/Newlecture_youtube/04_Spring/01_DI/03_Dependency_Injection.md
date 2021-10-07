## DI

: 종속성 주입, 부품 조립

- Composition has a (일체형)
    - b는 a의 **부품(dependency)**
    - a가 직접 객체 생성
    - a 객체 생성 시 부품이 같이 생성 됨
    - a의 부품 교체 어려움

    ```java
    class A{
    	private B b;
    	
    	public A(){
    		b = new B();
    	}
    }
    ```

- Association has a (조립형)
    - 외부에서 생성한 객체를 조립
    - b는 a의 dependency
    - setter를 통해 조립 (setter injection)
    - 생성자를 이용한 조립 (construction injection)

    ```java
    class A{
    	private B b;
    	
    	public A(B b){
    		this.b = b; //construction injection
    	}

    	public void setB(B b){
    		 this.b = b; //setter injection
    	}
    }
    ```

- 일체형보다 **조립형이 결합력이 낮다**
- 조립하는 과정이 **Dependency Injection**
- spring이 DI를 지원해준다