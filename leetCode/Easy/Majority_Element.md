## Majority Element

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
var majorityElement = function (nums) {
  let map = new Map();

  nums.map((e) => {
    if (map.get(e)) {
      map.set(e, map.get(e) + 1);
    } else {
      map.set(e, 1);
    }
  });

  let max = 0;
  let result = 0;

  for (let [key, value] of map) {
    if (max < value) {
      result = key;
      max = value;
    }
  }

  return result;
};
```

map을 이용하여서 각 숫자의 개수를 저장해줬다.  
저장한 후 for문을 이용해서 가장 큰 수의 값을 return 해줬다.

<hr/>

### :heavy_check_mark: 참고하면 좋은 다른 답안

Thanks for https://leetcode.com/problems/majority-element/discuss/1192865/Javascript-solution

```javascript
const majorityElement = (nums) => {
  const hashMap = new Map();

  for (let num of nums) {
    hashMap.set(num, (hashMap.get(num) || 0) + 1);

    if (hashMap.get(num) > nums.length / 2) {
      return num;
    }
  }
};
```

문제에 써있는게 n의 size/2이상이면 무조건 답인가보다.  
여러개 일줄알았다.

` hashMap.set(num, (hashMap.get(num) || 0) + 1);`  
넣는 부분에 || 연산자를 써서 if문을 줄였다.

<br/>
