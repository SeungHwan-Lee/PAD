# [Bon Appétit](https://www.hackerrank.com/challenges/bon-appetit/problem)
## Problem
```

```

## solve - javascript
```javascript
function bonAppetit(bill, k, b) {
    let sum = 0;
    for(let i=0; i<bill.length; i++) {
        if(i != k) sum += bill[i];
    }
    let rs = b-(sum/2);
    if(rs < 1) {
        console.log('Bon Appetit');
    }else {
        console.log(rs);
    }
}
```
