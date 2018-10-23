# [Diagonal Difference](https://www.hackerrank.com/challenges/diagonal-difference/problem)
## Problem
```
대각선 합계
```

## solve - javascript
```javascript
function diagonalDifference(arr) {
    const sums = [0, 0];
    const len = arr.length;
    for(let i=0,j=len-1; i<len; i++,j--) {
        sums[0] += arr[i][i];
        sums[1] += arr[i][j];
    }
    return Math.abs(sums[0]-sums[1]);
}
```
