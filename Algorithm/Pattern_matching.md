## 패턴매칭

- M개의 문자로 이루어져있는 문자열 x
- N의 문자로 이루어져있는 문자열 y
- x에 y가 포함되어있는지 알아보자

<br>

## 완전 탐색

- x의 문자 하나하나를 탐색하며 y의 첫문자와 동일한지 알아본다
- 동일하다면, 다음 문자가 같은가를 알아보며 y 문자열과 일치하는지 알아본다
- 다르다면, 다음 스타트 포인트로 이동하며 다시 살피어본다
- O(N*M)의 시간복잡도

<br>

## 라빈-카프 알고리즘

- **해시 값** 함수를 이용하여 문자열 검색
- y의 해시 값과 x의 하위 문자열의 해시 값만을 비교
- x의 하위 문자열의 해시 값을 구할 때, 전 해시 값을 이용하여 해시 값을 구한다 → sliding window 기법
- 문자열이 다르더라도 해시 값이 동일할 수 있기 때문에, 해시 값이 일치하면 문자열 일치 검사를 해야 한다 → 해시 값 충돌
- 유니크한 해시 값이 보장되어있다면, O(M)
- 해시 값 충돌이 일어난다면 최악의 경우에 O(M*N)

<br>

## 보이어 무어 알고리즘

- y문자의 끝쪽부터 비교
- 끝 문자가 불일치 하고 이 문자가 패턴 내에 존재할 경우, 패턴에 일치하는 문자를 찾아 skip
- skip 배열 만들기
- 최악의 시간복잡도: O(M*N)
- 최선의 시간 복잡도 O(N/M)

<br>

## KMP 알고리즘

- Knuth-Morris-Pratt Algorithm
- 불일치가 발생한 텍스트 문자열의 앞 부분에 어떤 문자가 있는지를 미리 알고 있으므로, 불일치가 발생한 앞 부분에 대하여 다시 비교하지 않고 매칭을 수행
- **부분 일치 테이블** 생성
- O(N+M)의 시간 복잡도

[1786번: 찾기](https://www.acmicpc.net/problem/1786)

```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.util.ArrayList;

public class BOJ_1786_찾기 {

	public static void main(String[] args) throws Exception {
		BufferedReader in = new BufferedReader(new InputStreamReader(System.in));
		StringBuilder sb = new StringBuilder();
		char[] text = in.readLine().toCharArray();
		char[] pattern = in.readLine().toCharArray();
		
		int tLength = text.length, pLength = pattern.length;
		
		// 부분일치테이블 만들기 : KMP의 아이디어를 똑같이 적용, W에서 W를 찾는 듯한 행위를 해서...
		int[] pi = new int[pLength]; //패턴 포인터를 어디로 옮겨야하는지 인덱스 저장
	    for(int i=1, j=0; i<pLength; i++){// i:접미사 포인터(i=1부터 시작: 우리는 실패함수를 만드는게 목적이므로 첫글자 틀리면 0위치로 가야하므로.), j:접두사 포인터
	        while(j>0 && pattern[i] != pattern[j]) {
	        	j = pi[j-1]; //j에서 문자가 다르다! -> j-1까지는 동일하다, pi[j-1]로 j 포인터를 이동
	        }
	        if(pattern[i]==pattern[j]) pi[i] = ++j; //j와 i는 일치하면 j 증가, 길이는 j+1
	        else pi[i] = 0; //일치하지 않는다면 j 그자리에
	    }
		
		int cnt = 0;
		// i : 텍스트 포인터 , j: 패턴 포인터 
		for(int i=0,j=0; i<tLength; ++i) { 
			
			while(j>0 && text[i] != pattern[j]) j = pi[j-1]; 
			
			if(text[i] == pattern[j]) { //두 글자 일치
				if(j == pLength-1) { // j가 패턴의 마지막 인덱스라면 
					cnt++; // 카운트 증가
					sb.append((i+1)-pLength+1).append('\n'); 
					j=pi[j]; 
				}else { // 패턴 앞쪽 일치하며 진행중인 상황
					j++;
				}
			}
		}
		
		System.out.println(cnt);
		System.out.println(sb);
	}

}
```