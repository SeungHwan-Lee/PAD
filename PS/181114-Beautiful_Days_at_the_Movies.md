# [Beautiful Days at the Movies](https://www.hackerrank.com/challenges/beautiful-days-at-the-movies/problem)
## Problem
```
i~j에서 (n-n.reverse)/k 정수인 개수
```

## solve - javascript
```javascript
function beautifulDays(i, j, k) {
    let count = 0;
    for(let n=i; n<=j; n++) {
        let num = (n - Number(n.toString().split("").reverse().join(""))) / k;
        if(num%1 == 0) count++;
    }
    return count;
}
```
