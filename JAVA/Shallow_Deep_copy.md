## 얕은 복사(shallow copy)

: 대입을 이용한 복사

```java
int[] a = {1,2,3,4,5,6,7};
int[] b = a;
b[1] = 1;
System.out.println(a[1]+" "+b[1]); //1 1
```

b의 원소 값을 변경하면 a의 원소 값도 변경됨 ⇒ a와 b가 **가리키는 객체가 동일**하다는 것!

<br/>

## 깊은 복사(deep copy)

: **다른 객체를 생성**하여 같은 값을 갖도록 한 것

다른 객체의 값을 변경해도 기존 객체의 값에 영향을 끼치지 않음

- [배열].clone()
- System.arraycopy(src, srcPos, dest, destPos, length)
    - src: 복사할 대상
    - srcPos: 복사할 대상의 시작 위치
    - dest: 붙여넣을 대상
    - destPos: 붙여넣을 대상의 시작 위치
    - length: 복사할 길이
- Arrays.copyOf(src, length)
- Arrays.copyOfRange(src, srcPos, length): srcPos 부터 length길이 만큼을 복사

<br/>

## 2차원 배열의 깊은 복사

→ arraycopy, clone 사용할 수 없음, for문 대입 혹은 1차원 배열을 반복하며 깊은 복사

```java
int[][] a = {{1,2,3}, {4,5,6}, {7,8,9}};
int[][] b = new int[3][3];

//for문을 이용한 대입
for(int i=0;i<3;i++){
	for(int j=0;j<3;j++){
		b[i][j] = a[i][j];
	}
}

//System.arraycopy 이용
for(int i=0;i<3;i++){
	System.arraycopy(a[i], 0, b[i], 0, a[i].length);
}

//1차원 배열 깊은 복사
for(int i=0;i<3;i++){
   b[i] = a[i].clone();
}
```