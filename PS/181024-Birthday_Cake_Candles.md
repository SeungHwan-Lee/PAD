# [Birthday Cake Candles](https://www.hackerrank.com/challenges/birthday-cake-candles/problem)
## Problem
```
초의 높이가 같은 최대 갯수
```

자료구조 map을 쓰면 쉽게 구해진다
## solve - javascript
```javascript
function birthdayCakeCandles(ar) {
    let max = 0;
    const list = {};
    for(let num of ar) {
        list[num] ? list[num]++ : list[num] = 1;
    }
    Object.keys(list).forEach(function(v){
        if(max < list[v]) max = list[v];
    });
    return max;
}
```
