# [Extra Long Factorials](https://www.hackerrank.com/challenges/extra-long-factorials/problem)
## Problem
```
큰 수 처리
```

## solve - javascript
```javascript
function extraLongFactorials(n) {
    const big = new Array(1000);
    for(let i=0; i<1000; i++) {
        big[i] = 0;
    }
    
    big[0] = 1;
    let len = 1;
    for(let i=2; i<=n; i++) {
        let carry = 0;
        for(let j=0; j<len; j++) {
            let mul = i*big[j] + carry;
            big[j] = mul % 10;
            carry = Math.floor(mul/10);
        }
        while(carry) {
            len++;
            big[len - 1] = carry % 10;
            carry = Math.floor(carry/10);
        }
    }
    
    let bigNum = [];
    if(big[len-1] != 0) bigNum.push(big[len-1]);
    for(let i=len-2; i>=0; i--) {
        bigNum.push(big[i]);
    }
    console.log(bigNum.join(''));
}
```
