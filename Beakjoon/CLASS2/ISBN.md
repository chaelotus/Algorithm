## 문제주소

> https://www.acmicpc.net/problem/14626

</br>

## 배운점

## 코드

```py
ISBN = input()

isbn_arr = [int(el) if el.isdigit() else el for el in ISBN]
sum = 0
check=0
m=-1


def calculate(idx):
    if idx%2==0:
        return 1
    else:
        return 3

for i in range(len(isbn_arr)):
    if isinstance(isbn_arr[i],int):
        sum+=(calculate(i)*isbn_arr[i])
    else:
        check=calculate(i)

for i in range(10):
    print('i',i)
    if (sum+(check*i))%10 == 0:
        print('if',i)
        m=i
        break


if m== -1:
    print(0)
else:
    print(m)
```
