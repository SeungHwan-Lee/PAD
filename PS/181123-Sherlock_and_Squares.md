# [Sherlock and Squares](https://www.hackerrank.com/challenges/sherlock-and-squares/problem)
## Problem
```

```

## solve - javascript
```javascript
function squares(a, b) {
    let count = 0;
    for (let i = 1; i < b; i++) {
        let n = i * i;
        if (b < n) break;
        if (a <= n && n <= b) count++;
    }
    return count;
}
```
