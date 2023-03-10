## 문제주소
>https://school.programmers.co.kr/learn/courses/30/lessons/120905

</br>

## 문제 접근 방법
배열의 각 요소에 n으로 나누었을 시 나머지가 있는 것을 제외한 것들을 filter()를 사용해 구하였다. 

</br>

### 아쉬운 점
.

</br>

## 코드
```
function solution(n, numlist) {
    return [...numlist].filter((x)=>x%n===0)
}
```
