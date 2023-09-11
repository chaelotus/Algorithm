## 문제주소

> https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/

</br>

## 문제 접근 방법
단순하게 먼저 최소값을 찾고 배열의 인덱스를 구하여 그 인덱스 이전의 값들을 0으로 바꾸고 최대값을 구하여 최대값에서 최소값을 뺀 값을 반환하였다. 만약 최소값이 제일 마지막 인덱스에 있으면 출력을 0으로 하였다. 

</br>

## 아쉬운 점
[2,4,1] 테스트 코드에서 잘못된 값을 반환하였다. 나는 단순히 제일 저렴한 가격일 때에만 구매할 수 있다고 생각하였다. 하지만 저렴한 가격에 사서 비싼 가격에서 파는 최대 값을 반환해야 하고 위의 테스트 케이스에서는 4-2 = 2가 나와야 한다.   
이것에 대한 솔루션은 left, right라는 변수를 만들어 left는 주식을 구매할 때, right는 주식을 판매할 때로 지정한다.  
[7,1,5,3,6,4] 에 대한 예시를 들어보자.  
left는 7, right는 1로 지정한다. 여기서는 left가 right보다 더 크므로 left를 right 위치로 이동하고 right는 1 증가한다.  
left는 1, right는 5이다. 여기서는 이익을 4를 얻게 된다.  
left는 1, right는 3이다. 여기서는 이익을 2를 얻게 된다. 하지만 이전의 이익보다 작으므로 갱신하지 않는다.  
left는 1, right는 6이다. 여기서는 이익을 5를 얻게 된다. 이전 이익보다 크므로 갱신한다.  
위와 동일한 방법으로 진행되고 최종적으로 이익을 5를 얻게 된다.
</br>

## 코드
내가 작성한 코드 
```js
var maxProfit = function(prices) {
  const min = Math.min(...prices);

  let index;
  for (let i = 0; i < prices.length; i++) {
    if (prices[i] === min) {
      index = i;
    }
  }
  let Price = [...prices];
  for(let i=0;i<index;i++){
    Price[i] = 0;
  }

  const max = Math.max(...Price);
  if (Price.indexOf(min) === prices.length) return 0;
  return max - min;
};
```
