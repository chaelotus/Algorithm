## 문제주소

> https://www.acmicpc.net/problem/11399

</br>

## 아쉬운점

조금만 더 생각을 해보았으면 되었을텐데..  
무작정 모든 경우의 수를 다 구하려고 했다. 하지만 한발짝 떨어져서 문제를 보면 앞에 대기자의 인출 시간이 줄어들면 전체적으로 시간이 줄어든다.  
즉 정렬하여 각 배열의 값을 구해주면 되는 쉬운 문제였다.

## 다른 사람이 푼 코드

```py

import sys

N = int(sys.stdin.readline())
p_arr = list(map(int,sys.stdin.readline().split()))

answer = 0
p_arr.sort()

for x in (len(p_arr)):
    answer+=sum(p_arr[0:x])

print(answer)
```
