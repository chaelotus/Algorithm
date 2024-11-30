## 문제주소

> https://www.acmicpc.net/problem/15829

</br>

### 아쉬운 점

처음 내가 시도한 코드에서 50점의 결과를 맞았다.  
일단 문제가 요구하는 바를 제대로 이해하지 않았던 것 같다.  
그리고 처음 코드에서는 객체를 만들어서 'a':1 key,value 형식으로 문제를 풀었다.  
사실 이렇게 객체를 정의하면서도 더 좋은 방법이 있을텐데 싶었다.  
다른 사람들의 코드를 확인해보니 알파벳을 쭉 적고 각 인덱스 번호를 사용할 수 있다는 것을 깨달았다.  
이후에 다시 푼 코드에서는 모두 더한 값에서 mod를 나눈 나머지 값을 출력해주니 100점이 나왔다.

## 다른 사람 코드

1차

```py
L = int(input())
list = input()

obj = {'a':1,'b':2,'c':3,'d':4,'e':5,'f':6,'g':7,'h':8,'i':9,'j':10,'k':11,'l':12,'m':13,'n':14,'o':15,'p':16,'q':17,'r':18,'s':19,'t':20,'u':21,'v':22,'w':23,'x':24,'y':25,'z':26}
sum = 0

for i in range(L):
    sum += obj.get(list[i])*pow(31,i)

print(sum)
```

2차

```py
L = int(input())
list = input()

alpha = 'abcdefghijklmnopqrstuvwxyz'
mod = 1234567891
sum = 0

for i in range(L):
    num = alpha.index(list[i])+1
    sum += num*pow(31,i)

print(sum% mod)
```
