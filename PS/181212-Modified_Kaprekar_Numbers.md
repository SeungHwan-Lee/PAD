# [Modified Kaprekar Numbers](https://www.hackerrank.com/challenges/kaprekar-numbers/problem)
## Problem
```

```

## solve - javascript
```javascript
function kaprekarNumbers(p, q) {
    const arr = [];
    for (let i = p; i <= q; i++) {
        if (isKaprekar(i)) {
            arr.push(i);
        }
    }
    if (arr.length != 0) console.log(arr.join(' '));
    else console.log('INVALID RANGE');
}
function isKaprekar(num) {
    const squared = num * num;
    const str = squared.toString();
    const left = str.substring(0, str.length / 2);
    const right = str.substring(str.length / 2);
    const numL = isEmpty(left) ? 0 : Number(left);
    const numR = isEmpty(right) ? 0 : Number(right);

    if (numL + numR == num) return true;
    else return false;
}
function isEmpty(str) {
    return (!str || 0 === str.length);
}
```
