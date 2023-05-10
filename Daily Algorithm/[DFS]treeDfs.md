## 문제

<img src="./img/treeDfs.png" style="width:300px">

</br>

## 문제 접근 방법

DFS 트리 문제를 js로 처음 풀어보아서 유튜브 강의를 참고하고 풀어보았는데 재귀함수를 이용하였다. 방문한 곳에는 node.vised의 값을 true로 주었다. 인접한 노드들에 for문을 돌려 dfs를 구현하였다.
</br>

## 아쉬운 점

나는 함수 자체를 재귀로 사용하여서 dfs 함수에서 바로 배열을 리턴을 할 수 없는 구조였다. 문제에서는 dfs 함수를 호출하면 배열의 값으로 반환이 되어야 되기 때문에 레퍼런스를 참고 하였는데 forEach문 안에서 dfs함수를 호출하고 concat 메서드를 사용해서 value 값을 계속 합쳐서 배열에 갱신하였다.

```js
let dfs = function (node) {
  let values = [node.value];

  node.children.forEach((x) => {
    values = values.concat(dfs(x));
  });
  return values;
};
```

</br>

## 내가 작성한 코드

```js
let dfs = function (node) {
  const print_array = [];
  // 현재 노드 방문했다면
  if (node.visited) return;
  node.visited = true;
  print_array.push(node.value);
  for (let i = 0; i < Object.keys(node.children).length; i++) {
    let mid = node.children[i];
    dfs(mid);
  }
};

// 이 아래 코드는 변경하지 않아도 됩니다. 자유롭게 참고하세요.
let Node = function (value) {
  this.value = value;
  this.children = [];
};

// 위 Node 객체로 구성되는 트리는 매우 단순한 형태의 트리입니다.
// membership check(중복 확인)를 따로 하지 않습니다.
Node.prototype.addChild = function (child) {
  this.children.push(child);
  return child;
};
```
