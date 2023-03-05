## 문제주소
>https://school.programmers.co.kr/learn/courses/30/lessons/120907

</br>

## 문제 접근 방법
'=' 기준으로 배열에 문자열을 넣어준다. 그럼 첫번째 값에는 예를들어 '3 + 5'가 있고 두번째 값에는 8이 있을 것이다. 문자열을 수식으로 바꿔주는 eval() 메서드를 사용하여 두 값이 같으면 O를, 다르다면 X를 넣어 문제를 풀었다.

</br>

### 아쉬운 점
어디서 eval() 메서드가 위험하다는 이야기를 들은 적 있는 것 같아 다른 방법으로 풀어보아도 괜찮을 것 같다.

</br>

## 코드
```
function solution(quiz) {
  var answer = [];
  let array = [];
    
  for (let i = 0; i < quiz.length; i++) {
    array[i] = quiz[i].split('=');

    if (eval(array[i][0]) === parseInt(array[i][1])) answer.push('O');
    else answer.push('X');
  }
 return answer;
}
```