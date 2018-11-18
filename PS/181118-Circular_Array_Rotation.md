# [Circular Array Rotation](https://www.hackerrank.com/challenges/circular-array-rotation/problem)
## Problem
```
k % a.length != 0 아닐때 마지막회전시 시작값 a.length - (k % a.length)
```

## solve - javascript
```javascript
function circularArrayRotation(a, k, queries) {
    const len = a.length;
    const start = len - (k % len);
    if(k%len != 0) {
        const temp = [];
        for(let i=0,j=0; i<len; i++) {
            if(start+i < len) temp[i] = a[start+i];
            else {
                temp[i] = a[j];
                j++;
            }
        }
        a = temp;
    }
    const result = [];
    for(let i=0; i<queries.length; i++) result[i] = a[queries[i]];
    return result;
}
```
