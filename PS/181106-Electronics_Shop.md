# [Electronics Shop](https://www.hackerrank.com/challenges/electronics-shop/problem)
## Problem
```
키보드와 USB의 최대가격
```

## solve - javascript
```javascript
function getMoneySpent(keyboards, drives, b) {
    let max = -1;
    for(let keyboard of keyboards) {
        for(let drive of drives) {
            let sum = keyboard + drive;
            if(b >= sum && max < sum) max = sum;
        }
    }
    return max;
}
```
