## ZigZag Conversion

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
/**
 * @param {string} s
 * @param {number} numRows
 * @return {string}
 */
var convert = function (s, numRows) {
  let result = '';
  let arr = [];

  for (let i = 0; i < numRows; i++) {
    let numArr = [];
    numArr.push(s[i]);
    arr.push(numArr);
  }

  let count = numRows - 1;
  let reverse = false;

  for (let i = numRows; i < s.length; i++) {
    if (count == numRows - 1 || count == 0) reverse = !reverse;

    if (numRows - 1 != 0) reverse ? count-- : count++;
    arr[count].push(s[i]);
  }

  arr.map((e) => (result += e.join('')));

  return result;
};
```

먼저 numRows의 길이만큼 배열을 생성해주고 arr에 넣어준다.  
reverse는 아래로 가면서 넣어줄지 위로가면서 넣어줄지를 체크한다.  
count는 처음에 생성한 배열 다음 글자의 index를 넣어준다.

만약에 count가 numRow길이만큼 오거나 0 일때 reverse를 바꿔줘서 넣는 순서를 바꿔준다.(count를 이용하여 줄이거나 늘리거나)  
그러고 arr을 합쳐준다.
`if (numRows - 1 != 0) reverse ? count-- : count++;` 은 2글자인 경우 걸려서 넣었는데.. 억지로 끼워넣은 느낌이라 좋지않다..  
차라리 시작할때 조건에서 걸러주면 좋을 것 같다.

<hr/>

### :heavy_check_mark: 참고하면 좋은 다른 답안

Thanks for https://leetcode.com/problems/zigzag-conversion/discuss/1165429/JS-solution-faster-99.65.-isIncreasing-switch

```javascript
var convert = function (s, numRows) {
  if (numRows === 1) return s;
  const res = new Array(numRows);
  res.fill('');

  let isIncreasing = true;
  let row = 0;
  for (let i = 0; i < s.length; i++) {
    res[row] += s[i];
    if (row === 0) isIncreasing = true;
    if (row === numRows - 1) isIncreasing = false;
    row += isIncreasing ? 1 : -1;
  }

  return res.join('');
};
```

배열에 배열을 넣지않고 바로 string으로 넣어준 풀이법이다.

<br/>
