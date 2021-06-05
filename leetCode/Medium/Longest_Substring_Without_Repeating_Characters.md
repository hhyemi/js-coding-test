## Longest Substring Without Repeating Characters

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
var lengthOfLongestSubstring = function (s) {
  let textArr = [];
  let lenArr = [];

  [...s].map((e) => {
    if (textArr.includes(e)) {
      lenArr.push(textArr.length);
      textArr.splice(0, textArr.indexOf(e) + 1);
    }
    textArr.push(e);
  });
  lenArr.push(textArr.length);
  return Math.max(...lenArr);
};
```

배열을 이용하여 해당글자가 있으면 일단 그 길이만큼 길이 배열에 넣어주고  
중복되는 글자의 index까지 splice해줬다.
if문 밖에 push는 겹치는 글자가 하나도 없을 경우를 위해 마지막에 길이배열에 넣어준다.

그러고 길이배열중 제일 큰 값을 return 해줬다.

<br/>
