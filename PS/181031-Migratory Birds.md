# [Migratory Birds](https://www.hackerrank.com/challenges/migratory-birds/problem)
## Problem
```
배열에서 많이 반복되는 숫자중에서 가장 작은수
```

## solve - javascript
```javascript
function migratoryBirds(arr) {
    const count = {};
    for(let n of arr) {
        if(count[n]) count[n]++;
        else count[n] = 1;
    }
    let max = 0;
    let min = 0;
    Object.keys(count).forEach(function(v){
        if(count[v] > max) {
            max = count[v];
            min = Number(v);
        }
    });
    Object.keys(count).forEach(function(v){
        if(count[v] == max)
            if(min > Number(v)) min = Number(v);
    });
    return min;
}
```
