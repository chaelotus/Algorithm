## 문제주소

> https://leetcode.com/problems/two-sum/solutions/3000141/javascript-w-map-time-space-o-n/

</br>

## 문제 접근 방법
이중 포문을 이용하여 두 숫자의 합이 target과 같은 인덱스 값을 result 배열에 넣어 반환하였다. 지금 생각해보면 if문 안에서 바로 return을 해주면 더 좋았을 것 같다.  

</br>

## 아쉬운 점
나의 코드는 시간 복잡도가 O(n^2)이다.  
솔루션에서 사람들이 많이 사용한 방법은 `Map`을 사용한 방법이다.  
`Map`은 키-값 쌍인 집합이고 키는 중복될 수 없다.  
이 문제에서 target에서 첫번째 값을 뺀 값이 두번째 값이 되는데, 그 두번째 값이 Map에 존재하는지 확인하고 해당 인덱스들을 구하면 된다.
</br>

## 코드
처음 작성한 코드 (이중 for문 O(n^2))
```js
var twoSum = function(nums, target) {
    let result = [];
    let numList = nums.slice();
 
    for(let i=0; i<numList.length; i++){
        for(let j=i+1; j<numList.length; j++){
            if(numList[i]+numList[j]===target){
                result.push(i)
                result.push(j);
            }
        }
    }
    return result;
};
```

솔루션 코드 (Map을 사용한 O(n))
```js
var twoSum = function(nums, target) {
    let map = new Map();

    for(let i=0; i<nums.length; i++){
        if(map.has(target-nums[i])){
            return [map.get(target - nums[i]),i];
        }
        else{
            map.set(nums[i],i);
        }
    }
};
```