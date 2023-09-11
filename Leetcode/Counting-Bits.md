## 문제주소

> https://leetcode.com/problems/contains-duplicate/description/

</br>

## 문제 접근 방법
javascript의 Set을 사용하여 문제를 풀었다. Set은 중복되어 있는 숫자를 제거해주는 역할을 한다. Set을 사용하여 중복되어 있는 숫자를 제거한 배열의 길이와 원래 배열의 길이를 비교하여 같으면 false, 다르면 true를 반환하였다.

</br>

## 아쉬운 점

</br>

## 코드
내가 작성한 코드 
```js
var containsDuplicate = function(nums) {
    let numsList = new Set([...nums]);

    if(numsList.size === nums.length) return false
    else return true;
};
```
