## 문제주소

> https://www.acmicpc.net/problem/15552

</br>

## 주의할 점

보통 한 두줄 입력받는 문제들과 다르게, 반복문으로 여러줄을 입력 받아야 할 때는 input()으로 입력 받는다면 시간초과가 발생할 수 있다.
이떄는 input()대신 `sys.stdin.readline`을 사용하자.

## 코드

```py
import sys

num = int(input())

for i in range(num):
    x,y = map(int,sys.stdin.readline().split())
    print(x+y)
```
