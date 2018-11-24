# [Library Fine](https://www.hackerrank.com/challenges/library-fine/problem)
## Problem
```

```

## solve - javascript
```javascript
function libraryFine(d1, m1, y1, d2, m2, y2) {
    const nowDate = new Date(y1, m1 - 1, d1);
    const lastDate = new Date(y2, m2 - 1, d2);
    let price = 0;
    if (lastDate.getTime() < nowDate.getTime()) {
        if (y1 == y2 && m1 == m2) price = 15 * (d1 - d2);
        else if (y1 == y2)        price = 500 * (m1 - m2);
        else                      price = 10000;
    }
    return price;
}
```
