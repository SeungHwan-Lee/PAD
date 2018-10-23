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
    const check = [false, false];
    
    for(let num of arr) {
        if(min > num) min = num;
        if(max < num) max = num;
    }
    for(let num of arr) {        
        if(num != max || check[0]) result[0] += num;
        else check[0] = true;
            
        if(num != min || check[1]) result[1] += num;
        else check[1] = true;
    }
    
    console.log(result.join(' '));
}
```
