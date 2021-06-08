## Find All Numbers Disappeared in an Array

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
var findDisappearedNumbers = function (nums) {
  let big = nums.length;

  let arr = [];

  for (let i = 1; i <= big; i++) {
    if (!nums.includes(i)) arr.push(i);
  }

  return arr;
};
```

<hr/>

### :heavy_check_mark: 참고하면 좋은 다른 답안

Thanks for https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/submissions/

```javascript
var findDisappearedNumbers = function (nums) {
  let res = [];
  let len = nums.length;
  let set = new Set(nums); // [1,2,3,4,7,8];
  for (let i = 1; i <= len; i++) {
    if (!set.has(i)) res.push(i);
  }
  return res;
};
```

set을 이용한 코드이다.

<br/>
