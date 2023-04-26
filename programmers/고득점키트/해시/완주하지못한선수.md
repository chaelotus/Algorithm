## 문제주소

> https://school.programmers.co.kr/learn/courses/30/lessons/42576

</br>

## 문제 접근 방법

이번이 두번째 푼 문제이다. 첫번째에는 객체로 어떻게 도전을 하였는데 실패하였다. 스터디 분들과 다른 사람 문제 풀이를 봤는데 생성자 함수 Map을 사용하셨다.  
그때 Map이라는 함수에 대해 사용하는 방법을 알게 되었고 이번에 Map을 이용해 풀었다.  
아직 조금 더 익숙해져야 할 듯하다.
</br>

## 아쉬운 점

map 에 key와 value 값을 찾기 위해서 처음에 작성한 코드는 이렇다.

```js
for (let list of map.entries()) {
  if (list[1] === 2) return list[0];
  else if (list[1] === 0) return list[0];
}
```

이렇게 하니 테스트를 통과하지 못한것이 2개 있었고 또한 효율성 테스트도 통과하지 못하였다.  
다시 한 번 찾아보니 밑의 코드처럼 아주 쉽게 찾아올 수 있는 방법이 있었다.

```js
for (let [k, v] of map) {
  if (v > 0) return k;
}
```

</br>

## 코드

```js
function solution(participant, completion) {
  let map = new Map();

  for (let i = 0; i < participant.length; i++) {
    map.set(participant[i], (map.get(participant[i]) || 0) + 1);
    map.set(completion[i], (map.get(completion[i]) || 0) - 1);
  }

  for (let [k, v] of map) {
    if (v > 0) return k;
  }
}
```
