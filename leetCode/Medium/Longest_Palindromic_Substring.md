##

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript

```

### 사용함수

-

<hr/>

### :heavy_check_mark: 참고하면 좋은 다른 답안

Thanks for

```javascript
var longestPalindrome = function (s) {
  let maxLen = '';

  const check = (i, j) => {
    while (i >= 0 && s[i] == s[j]) {
      i--;
      j++;
    }

    i++;
    j--;

    if (maxLen.length < j - i + 1) {
      maxLen = s.slice(i, j + 1);
    }
  };

  for (let i = 0; i < s.length; i++) {
    check(i, i);
    check(i, i + 1);
  }

  return maxLen;
};
```

처음에 풀었는데 시간초과가 나와서 다른사람 풀이법을 참고했다 ㅠㅠ..  
봐도 이해하기가 어려웠다.  
check함수를 2번하는 이유는 짝수, 홀수길이일때를 확인하기 위해서다..

while문을 이용해서 같을때까지 체크를 해주고 maxLen비교후 넣어준다.

<br/>
