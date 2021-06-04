##

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
var removeElement = function (nums, val) {
  nums = nums.filter((e) => e != val);
  return nums.length;
};
```

filter함수가 안된다길래 왜인지 찾아보니까 새로운 배열을 리턴하면 안된다는게 문제였다..흠ㅠ

```javascript
var removeElement = function (nums, val) {
  for (let i = 0; i < nums.length; i++) {
    if (nums[i] === val) {
      nums.splice(i, 1);
      i--;
    }
  }
  return nums.length;
};
```

for문을 이용해서 풀어줬다.
splice를 했으니 index를 줄여주는것을 잊지말자

<br/>
