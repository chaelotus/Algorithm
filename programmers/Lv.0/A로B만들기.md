## 문제주소
>https://school.programmers.co.kr/learn/courses/30/lessons/120886

</br>

## 문제 접근 방법
includes 메서드를 사용하기 위해 before, after 둘 다 배열로 만들었다. 처음에는 단순히 포함되어있는지만 체크하였는데 그렇게 되면 before에 p가 2개 있고 after에 p가 1개만 있어도 포함이 되는 것이 원하는 답이 나오지 않았다.   
그래서 비교한 문자가 포함되어 있으면 그 값을 삭제 하다가 만약 false가 나오면 0으로 리턴되게 하였다.

</br>

### 아쉬운 점
나는 이 문제를 보고 set 이나 includes가 생각이 났는데 다른 사람들의 풀이를 보고 깜짝 놀랐다.   
정말 단순하게 before과 after을 각각 sort하여 같은지 비교하면 되는 간단한 방법이 있었다..!🤭

</br>

## 코드
```
function solution(before, after) {

  let $before = before.split('');
  let $after = after.split('')

  for(let i=0;i<before.length;i++){
    if($before.includes($after[i])){
      $before.splice($before.indexOf($after[i]),1);
    }else{
      return 0;
    }
  }
  return 1;
}
```