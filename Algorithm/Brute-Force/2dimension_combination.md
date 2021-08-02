```java
//map[N][M] 배열에서 3개를 뽑을 때

void comb(int start, int num){
	if(num == 3){
			return;
	}
	
	for(int i=start; i<N*M; i++){
		int col = i/M;
		int row = i%M;
		
		if(map[col][row] == 0){
			map[col][row] = 1;
			comb(start+1, num++)
		}
	}
}
```