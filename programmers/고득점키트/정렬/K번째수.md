## 문제주소

> https://school.programmers.co.kr/learn/courses/30/lessons/42748

</br>

## 문제 접근 방법

commands에 있는 배열의 수 만큼 반복문을 돌려 slice 메서드를 사용해 필요한 부분만 추출하고 정렬한 뒤 answer 배열에 값을 넣어주었다.
</br>

</br>

## 코드

```js
function solution(array, commands) {

  let answer = [];
  for(let i=0;i<commands.length;i++){
    let arr = array.slice(commands[i][0]-1,commands[i][1]).sort((a,b)=>a-b)
    answer.push(arr[commands[i][2]-1])
  }
  return answer;
}
```
