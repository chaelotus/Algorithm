## 문제주소

> https://www.acmicpc.net/problem/10871

</br>

## 주의할 점

파이썬은 `print`로 출력하면 줄바꿈이 된다. 줄바꿈을 하지 않기 위해서는 `end=""`를 붙여주자.

## 코드

```py
N, X = map(int, input().split())
A = []

A = list(map(int, input().split()))

for i in range(N):
    if(X>A[i]):
        print(str(A[i])+" ", end="")
```
