# [The Hurdle Race](https://www.hackerrank.com/challenges/the-hurdle-race/problem)
## Problem
```
물약 개수 구하기
```

## solve - javascript
```javascript
function hurdleRace(k, height) {
    let max = Number.MIN_SAFE_INTEGER;
    for(let n of height) {
        if(max < n) max = n;
    }
    return max > k ? max-k : 0;
}
```
