## 문제주소

> https://school.programmers.co.kr/learn/courses/30/lessons/12954

</br>

## 문제 접근 방법

for문을 n개의 갯수만큼 돌리고 변수 초기값이 x인 num을 만들어 배열에 넣어주었다.

</br>

## 아쉬운 점

다른 사람들의 풀이를 보니 n개의 배열을 만들어 놓고 거기서 x의 수만큼 커지는 수를 채우는 방법을 쓰였는데 이러한 방법을 사용할 줄 아는데도 생각하지 못한 것이 아쉽다.

```js
Array(n)
  .fill(x)
  .map((v, i) => (i + 1) * v);
```

</br>

## 코드

```
function solution(x, n) {
  let array = [];
  let num = x;
  for (let i=0;i<n;i++) {
    array.push(num)
    num+=x
  }
  return array;
}
```
