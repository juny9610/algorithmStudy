# 동적 프로그래밍(Dynamic Programming)
> 반복적으로 계산되는 것들의 계산 횟수를 줄이기 위해 값을 저장해두었다가 재사용하는 기법이다.



## 예제 문제

### [백준 9251번 LCS](./9251_LCS.cpp)
`최장 공통 부분 수열(LCS)` 문제로, 기본적인 DP 문제의 예제이다.  
두 개의 문자열에서 순서대로 겹치는 문자가 최대 몇 개인지 구하는 문제이다.  

### [백준 9252번 LCS 2](./9252_LCS2.cpp)
9251번과 같은 `LCS` 문제이다.  
LCS의 길이에 LCS 문자열까지 출력하면 된다.  

### [백준 1915번 가장 큰 정사각형](./1915_가장큰정사각형.cpp)
1로 이루어진 가장 큰 정사각형의 크기를 구하는 문제이다.  
`(i,j)`에서 `(i-1,j), (i,j-1), (i-1,j-1)` 세가지를 확인한 후, 가장 작은 수에 +1 해주면 된다.  

### [백준 12865번 평번함 배낭](./12865_평범한배낭.cpp)
전형적인 `배낭 알고리즘(Knapsack Algorithm)` 이다.  
배낭에 담을 수 있는 무게의 최댓값이 정해져 있고, 일정 가치와 무게가 있는 짐들을 배낭에 넣을 때, 가치의 합이 최대가 되도록 짐을 고르는 방법을 찾는 알고리즘을 뜻한다.  
**Knapsack 기본 코드**
``` c++
    for(int i = 1; i <= N; i++) {
        for(int j = 1; j <= K; j++) {
            if(j >= weigh[i]) dp[i][j] = max(dp[i-1][j], dp[i-1][j-weigh[i]] + value[i]);
            else dp[i][j] = dp[i-1][j];
        }
    }
```

### [백준 1520번 내리막길](./1520_내리막길.cpp)
시작점에서 더 낮은 숫자들로만 가서 마지막 좌표까지 갈 수 있는 경로의 갯수를 출력하는 문제이다.  
단순 dfs로 풀면 시간초과가 날 수 있기 때문에, `dfs + dp` 를 이용했다.  


### [백준 11054번 가장 긴 바이토닉 부분 수열](./11054_가장긴바이토닉부분수열.cpp)
`가장 긴 증가하는 부분 수열 + 가장 긴 감소하는 부분 수열` 이라고 생각하면 된다.  

### [백준 1005번 ACM Craft](./1005_ACMcraft.cpp)
`위상 정렬 (Topological Sort)`의 대표적인 문제이다.  
위상 정렬은 그래프의 각 노드를 어떤 순서대로 방문할 때, 반드시 선행 노드가 이미 모두 방문되어야 하는 조건을 만족하는 `노드 방문 순서`를 결정하는 정렬이다.  
선행 노드가 하나 이상 존재하는 노드의 **최소 건설 시간**은 선행 노드들의 최소 건설 시간들 중의 **최댓값**이다.  

### [백준 10942번 펠린드롬?](./10942_펠린드롬?.cpp)
**펠린드롬(palindrome)**이란 앞에서 읽으나 뒤에서 읽으나 같은 단어를 말한다.  
S와 E 사이의 거리를 계산한 후 배열을 갱신해준다.