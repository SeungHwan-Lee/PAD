# [Sock Merchant](https://www.hackerrank.com/challenges/sock-merchant/problem)
## Problem
```

```

## solve - javascript
```javascript
function sockMerchant(n, ar) {
    let map = {};
    let count = 0;
    for(let num of ar) {
        if(!map[num]) map[num] = 1;
        else map[num]++;
    }
    Object.keys(map).forEach(function(v){
        count += Math.floor(map[v]/2);
    });
    return count;
}
```
