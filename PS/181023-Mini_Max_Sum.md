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
    const result = [0, 0];
    
    for(let num of arr) {
        if(min > num) min = num;
        if(max < num) max = num;
        result[0] += num;
        result[1] += num;
    }
    result[0] -= max;
    result[1] -= min;
    
    console.log(result.join(' '));
}
```
