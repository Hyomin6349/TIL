## 순열(Permutation)

: 서로 다른 것들 중 몇 개를 뽑아서 한 줄로 나열하는 것

- $nPr$ = $n * (n-1) * (n-2) * ... * (n-r+1)$
- $nPn = n!$

```java

//nPr
void Permutation(int cnt){
	if(cnt==r) return; //다 뽑음
	
	for(int i=0; i<n; i++){ //가능한 모든 수 시도
		if(!isSelected[i]){
			numbers[cnt] = i;
			isSelected[i] = true;
			Permutation(cnt+1);
			isSelected[i] = false;
		}
	}
}
```

<br/>

## 조합과 비교

```java
//nCr
void Combination(int cnt, int start){
	if(cnt==r) return; //다 뽑음
	
	//앞에서 시도한 위치의 다음부터 => 중복 상황 x, 같은 수 선택 x 
	for(int i=start; i<n; i++){ 
			numbers[cnt] = i;
			Combination(cnt+1, start+1);
	}
}
```