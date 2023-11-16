## 문제주소

> https://school.programmers.co.kr/learn/courses/30/lessons/12900
</br>

## 문제 접근 방법
제한 시간안에 문제를 풀지 못하여 기록하는 오답노트입니다.  
처음에는 직사각형이 채워지는 걸 어떻게 다 구하나 싶었습니다.  
다른 사람의 풀이를 보았더니 피보나치 수열을 이용하여 풀었습니다. 다시 확인해보니 n=1일때는 1, n=2일때는 2, n=3 3, n=4 5, n=5 8로 피보나치 수열로 증가하였습니다.  
보통 피보나치 수열을 재귀로 구현할 때 콜스택에 무리가 간다고 합니다.(동일한 계산을 반복)  
이러 문제점을 해결하기 위해 메모이제이션 방식을 사용한다고 합니다.(DP와 유사)
</br>

</br>

## 코드
다른 사람이 푼 코드
```js
function solution(n) {
  return fibonacci(n);
}

const fibonacci = (n) => {
  const dp = new Array(n+1).fill(0);
  dp[0] = 1;  dp[1] = 1;
  
  for(let i = 2; i <= n; i++) {
    dp[i] = (dp[i-2] + dp[i-1]) % 1000000007;
  }
  
  return dp[n];
}

```
