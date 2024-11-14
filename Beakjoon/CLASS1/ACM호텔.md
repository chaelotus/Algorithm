## 문제주소

> https://www.acmicpc.net/problem/10250

</br>

## 코드

```py
T = int(input())


for i in range(T):
    Y = 1
    XX = 1
    H, W, N = map(int,input().split())
    while(H < N):
        N -= H
        XX += 1

    if(XX>=10):
         print(str(N)+str(XX))
    elif(XX<10):
        print(str(N)+'0'+str(XX))
```
