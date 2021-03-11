## 문자열 내 p와 y의 개수

<hr/>

### :heavy_check_mark: 내가 푼 답안

```javascript
function solution(s) {
  let pCnt = 0,
    yCnt = 0;
  s = s.toLowerCase();

  for (let i in [...s]) {
    if (s.charCodeAt(i) == 112) {
      pCnt++;
    } else if (s.charCodeAt(i) == 121) {
      yCnt++;
    }
  }
  if (pCnt == yCnt) {
    return true;
  }

  return false;
}
```

`s.toLowerCase()`로 소문자로 다 바꿔주고  
아스키코드를 이용해서 같을때 count를 써줘서 비교해줬다.

<hr/>

### :heavy_check_mark: 참고하면 좋은 다른 답안

Thanks for https://programmers.co.kr/learn/courses/30/lessons/12916/solution_groups?language=javascript&type=all

```javascript
function numPY(s) {
  return (
    s.toUpperCase().split('P').length === s.toUpperCase().split('Y').length
  );
}
```

split함수를 이용해서 length를 비교해준 코드이다.  
해당 문자가 많으면 배열의 길이가 늘어나니까.. 생각도 못했다.

<hr/>

### :heavy_check_mark: 참고하면 좋은 다른 답안2

Thanks for https://programmers.co.kr/learn/courses/30/lessons/12916/solution_groups?language=javascript&type=all

```javascript
function numPY(s) {
  var result = true;
  s = s.toUpperCase();
  var num = 0;
  for (var i = 0; i < s.length; i++) {
    if (s[i] === 'P') num++;
    if (s[i] === 'Y') num--;
  }
  result = num === 0;

  return result;
}
```

아스키코드말고 문자열 비교해주면되는데 바보였다..  
num을 p일때 ++ 해주고 y일때 -- 해준방식이 맘에든다.

<br/>
