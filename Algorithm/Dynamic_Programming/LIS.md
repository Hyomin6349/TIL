## 최장 증가 수열

: 배열의 순서를 유지하면서 크기가 점진적으로 커지는 가장 긴 부분 수열의 길이를 구하는 문제

<br>

## DP 접근 방법

1. LIS(i): i 번째 원소까지 **고려한** 최장부분수열 길이 

    → 어떤 원소가 마지막으로 서있는지 모르기 때문에 i 번쨰 원소를 붙일 수 있는지 없는지 알 수 없다

2. LIS(i): i 번째 원소를 **끝으로 하는** 최장부분수열 길이
    - LIS(i) = **0 ~ i-1 까지의 LIS 중 자신 보다 작은 원소 중 가장 큰 LIS를 구하여 + 1**
    - 자신보다 작은 원소 = 자신이 뒤에 설 수 있는 원소들 중
    - 가장 큰 LIS = 최장부분수열 길이를 가진 → 자신의 LIS를 갱신하며 원소 탐색
    - +1 = i 번째 원소를 뒤에 세우기

<br>

## 코드

```sql
for(int i=0;i<N;i++) {
			LIS[i] = 1;
			
	for(int j=0;j<i;j++) {
		if(arr[j]<arr[i] && LIS[j]+1 > LIS[i]) {
			LIS[i] = LIS[j] + 1;
		}
	}
	
	if(max < LIS[i]) max = LIS[i];
}
```

- 각 원소의 LIS는 적어도 1 값은 가짐 → 자기 자신만 세우는 수열
- LIS[i]를 조건을 만족하는 j에 대해 **업데이트** 해주는 방식으로 진행
- O(N*N)의 시간복잡도

<br>

## DP 접근 방법 2

- 같은 길이의 LIS 중에 가장 끝 원소가 작을 수록 뒤에 원소를 넣기에 유리하다
- LIS[i]: i 길이의 증가 수열 중 맨 끝을 최소값으로 유지
- i 번째 원소를 고려
    1. 만들어 놓은 LIS 뒤에 넣을 수 있다 → 넣기
    2. LIS 뒤에 넣을 수 없다 

        → 앞의 LIS 원소 중 i 번째 원소와 대체할 수 있는 부분을 찾기 ⇒ **이진 탐색** 이용

- O(N*logN): N개의 원소에 대해 이진탐색(O(logN)) 수행

<br>

## 코드

```sql
//중복값이 없는 arr
int size = 0;// LIS에 채워진 원소 수
for(int i=0;i<N;i++) {
	int temp = Math.abs(Arrays.binarySearch(LIS, 0, size, arr[i]))-1; //중복 값이 없으니 항상 음수 반환
	LIS[temp] = arr[i];
	
	if(temp==size) size++; //추가된 위치가 맨 끝이라면 size 증가
}
```