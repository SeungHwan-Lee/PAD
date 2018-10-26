# [Kangaroo](https://www.hackerrank.com/challenges/kangaroo/problem)
## Problem
```
같은 지점에 도달하는지 확인
```

## solve - javascript
```javascript
function kangaroo(x1, v1, x2, v2) {
    while(x1<x2 && v1>v2) {
        x1 += v1;
        x2 += v2;
    }
    return x1==x2 ? 'YES' : 'NO';
}
```
