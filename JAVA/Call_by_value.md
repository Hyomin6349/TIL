## Call by Value

```java
Class CallByValue{

		public static void swap(int x, int y) {
				int temp = x;
				x = y;
				y = temp;
		}
		
		
		
		public static void main(String[] args) {
		
		int a = 10;
		int b = 20;
		
		System.out.println("swap() 호출 전 : a = " + a + ", b = " + b);
		
		swap(a, b);
		
		System.out.println("swap() 호출 후 : a = " + a + ", b = " + b);
		}

}
```

- 호출 전이나 호출 후나 a = 10, b = 20 라고 출력된다
- 메서드에 **값만 복사**돼서 전달되었기 때문

<br>

## Call by Reference

```java
Class Reference {
	int value;
	public Reference (int value) {
		this.value = value;
	}
}

Class CallByValue{

	public static void swap(Reference x, Reference y) {
		int temp = x.value;
		x.value = y.value;
		y.value = temp;
	}
	
	
	
	public static void main(String[] args) {
	
	Reference a = new Reference(10);
	Reference b = new Reference(10);
	
	System.out.println("swap() 호출 전 : a = " + a + ", b = " + b);
	
	swap(a, b);
	
	System.out.println("swap() 호출 후 : a = " + a + ", b = " + b);
	}

}
```

- 이때는 값이 변경된다
- **주소값이 전달**되어 주소를 참조하는 값을 변경하기 때문
- 하지만 결국 참조형 변수의 값은 주소값이 저장되는 것이고 그 값이 전달된다는 관점에서 call by value라고 할 수 있다.
