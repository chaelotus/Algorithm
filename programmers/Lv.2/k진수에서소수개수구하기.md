## 문제주소

> https://school.programmers.co.kr/learn/courses/30/lessons/92335

</br>

## 문제 접근 방법

k진수로 변환해준 후 0으로 배열을 구분하고 소수를 구분하는 함수에서 true인 값들만 카운팅하였다.
</br>

## 아쉬운 점

처음에 문제를 굉장히 어렵게 생각해서 코드를 되게 복잡하게 구현했다.  
(문제의 요지를 알 지 못하였다.)  
이 코드도 너무 복잡하게 풀어 어느 정도 스터디 팀장님께서 살짝 손을 봐주셨다.  
하지만 1번 테스트가 계속 시간초과가 나서 대체 왜그럴까 하고 봤는데 팀장님이 소수 구하는 함수에서 `i<=Math.sqrt(num)`을 해줘야 한다고 하셨다.  
사실 이 부분을 알고는 있었지만 굳이 하지 않았는데 숫자가 커질수록 많은 시간이 걸려 이런 사소한 것 까지 신경을 써야 되구나라고 느꼈다.

</br>

## 코드

```js
function isPrime(num) {
  if (num < 2) return false;

  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) {
      return false;
    }
  }
  return true;
}

function solution(n, k) {
  let decimal = n.toString(k);

  const array = decimal.split(0);

  let count = 0;
  for (let i = 0; i < array.length; i++) {
    if (isPrime(array[i])) {
      count++;
    }
  }

  return count;
}
```
