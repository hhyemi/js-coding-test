## x만큼 간격이 있는 n개의 숫자

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
function solution(x, n) {
  var answer = [];

  for (let i = 1; i <= n; i++) {
    answer.push(x * i);
  }

  return answer;
}
```

<hr/>

### :heavy_check_mark: 참고하면 좋은 다른 답안

Thanks for https://programmers.co.kr/learn/courses/30/lessons/12954/solution_groups?language=javascript

```javascript
function solution(x, n) {
  return Array(n)
    .fill(x)
    .map((v, i) => (i + 1) * v);
}
```

미리 배열을 만들어놓고 x로 다 채운다음에 계산해주는 방식이다.

### arr.fill(value[, start[, end]])

- value : 배열을 채울 값.
- start Optional :시작 인덱스, 기본 값은 0.
- end Optional :끝 인덱스, 기본 값은 this.length.

출처 :[https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/fill](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/fill)

<br/>
