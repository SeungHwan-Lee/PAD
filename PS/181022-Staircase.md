# [Staircase](https://www.hackerrank.com/challenges/staircase/problem)
## Problem
```
계단 출력
```

## solve - javascript
```javascript
function staircase(n) {
    for(let i=0; i<n; i++) {
        let list = [];
        for(let j=0; j<n-i-1; j++) list.push(' ');
        for(let j=0; j<i+1; j++) list.push('#');
        console.log(list.join(''));
    }
}
```
