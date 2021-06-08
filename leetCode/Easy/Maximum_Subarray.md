## Maximum Subarray

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
var maxSubArray = function (nums) {
  let maxNum = nums[0];
  let sum = 0;

  for (let i = 0; i < nums.length; i++) {
    sum = 0;
    sum += nums[i];
    if (maxNum < sum) maxNum = sum;
    for (let j = i + 1; j < nums.length; j++) {
      sum += nums[j];
      if (maxNum < sum) maxNum = sum;
    }
  }

  return maxNum;
};
```

<hr/>

### :heavy_check_mark: 참고하면 좋은 다른 답안

Thanks for https://leetcode.com/problems/maximum-subarray/discuss/380007/JavaScript-beats-99-super-simple

```javascript
var maxSubArray = function (nums) {
  for (let i = 1; i < nums.length; i++) {
    nums[i] = Math.max(nums[i], nums[i] + nums[i - 1]);
  }
  return Math.max(...nums);
};
```

if문 비교 대신에 Math.max를 이용한 코드이다.

<br/>
