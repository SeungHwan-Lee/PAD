# [Find Digits](https://www.hackerrank.com/challenges/find-digits/problem)
## Problem
```

```

## solve - javascript
```javascript
function findDigits(n) {
    let r = n;
    let count = 0;
    let digit = 0;
    while (r > 0) {
        digit = r % 10;
        r = Math.floor(r/10);
        if (digit > 0 && n % digit == 0) count++;
    }
    return count;
}
```
