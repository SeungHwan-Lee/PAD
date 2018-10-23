# [Mini-Max Sum](https://www.hackerrank.com/challenges/mini-max-sum/problem)
## Problem
```
최소값과 최대값 출력
```

## solve - javascript
```javascript
function miniMaxSum(arr) {
    let min = Number.MAX_SAFE_INTEGER;
    let max = Number.MIN_SAFE_INTEGER;
    let sum = 0;
    
    for(let num of arr) {
        if(min > num) min = num;
        if(max < num) max = num;
        sum += num;
    }
    
    console.log(`${sum-max} ${sum-min}`);
}
```
