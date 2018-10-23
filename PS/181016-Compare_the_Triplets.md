# [Compare the Triplets](https://www.hackerrank.com/challenges/compare-the-triplets/problem)
## Problem
```
각각의 스코어
```

## solve - javascript
```javascript
function compareTriplets(a, b) {
    const result = [0, 0];
    
    for(let i=0; i<a.length; i++) {
        if(a[i] > b[i]) {
            result[0]++;
        }else if(a[i] < b[i]) {
            result[1]++;
        }
    }
    
    return result;
}
```
