## 문제주소

> https://school.programmers.co.kr/learn/courses/30/lessons/42747

</br>

## 문제 접근 방법

참고하기

- https://en.wikipedia.org/wiki/H-index
- https://www.ibric.org/myboard/read.php?Board=news&id=270333

인덱스 숫자와 해당 값이 같은 값이면 그 값을 리턴  
또는 인덱스보다 값이 작아지기 시작하면 그 전 인덱스 값 리턴  
위의 두개의 경우 해당되지 않으면 배열의 길이 리턴
</br>

</br>

## 코드

```js
function solution(citations) {
  citations.sort((a, b) => b - a);

  for (let i = 0; i < citations.length; i++) {
    if (i + 1 === citations[i]) {
      return i + 1;
    } else if (i + 1 > citations[i]) {
      return i;
    }
  }
  return citations.length;
}
```
