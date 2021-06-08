## Sorting the Sentence

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
var sortSentence = function (s) {
  let arr = s.split(' ');
  let result = [];

  for (let i = 1; i <= arr.length; i++) {
    for (let j = 0; j < arr.length; j++) {
      if (arr[j].includes(i + '')) {
        result.push(arr[j].substr(0, arr[j].length - 1));
      }
    }
  }

  return result.join(' ');
};
```

배열에 담아주고 for문을 이용하여 숫자가 포함되면 result에 넣어줬다(이때 맨마지막 숫자는 자른다.)

<hr/>

### :heavy_check_mark: 참고하면 좋은 다른 답안

Thanks for https://leetcode.com/problems/sorting-the-sentence/discuss/1232525/Javascript-or-Simple-Solution

```javascript
var sortSentence = function (s) {
  s = s.split(' ');
  let newk = [];
  for (let i of s) {
    newk[i.slice(-1) - 1] = i.slice(0, -1);
  }
  return newk.join(' ');
};
```

처음부터 넣을때 배열에 넣어주면 되는거였다..

<br/>
