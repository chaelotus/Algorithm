## 문제주소

> https://www.acmicpc.net/problem/28702

</br>

## 아쉬운 점

입력받은 문자열을 배열에 넣고 제일 마지막에 오는 숫자의 값과 인덱스 번호를 알려고 했다. 이를 구현하는 과정에서 filter 함수를 사용을 하려고 하였는데 별로 좋은 방법이라고 생각하지는 않았다. 다른 사람의 풀이를 보니 역순으로 for문을 돌려서 Fizz, Buzz, FizzBuzz가 아닌 것 중에 제일 처음 만나는 숫자에 i를 더해서 다음 올 수를 구할 수 있었다. 그리고 그 숫자를 if문을 통해 출력해주면 된다.  
쉬운 문제였는데 아직 파이썬으로 구현을 하는데에 있어서 어려움을 느끼는 것 같다.

## 코드

```py
for i in range(3,0,-1):
    x = input()
    if x not in ['Fizz','Buzz','FizzBuzz']:
        n = int(x) + i
        break

if n%3==0 and n%5==0:
    print('FizzBuzz')
elif n%3==0:
    print('Fizz')
elif n%5==0:
    print('Buzz')
else:
    print(n)
```
