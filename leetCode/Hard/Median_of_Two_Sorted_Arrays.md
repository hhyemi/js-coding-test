##

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
var findMedianSortedArrays = function (nums1, nums2) {
  let numArr = nums1.concat(nums2);
  numArr.sort((x, y) => x - y);

  let mid = Math.floor(numArr.length / 2);

  if (numArr.length % 2 == 0) {
    return (numArr[mid - 1] + numArr[mid]) / 2;
  } else {
    return numArr[mid];
  }
};
```

두 배열을 합쳐주고 sort를 시켜줬다.  
그러고 홀수 일때 짝수일때를 계산해줬다.  
마지막 if문은  
`return numArr.length % 2 ? numArr[mid] :(numArr[mid-1]+ numArr[mid]) /2`
한줄로 요약이 가능하다.

<br/>
