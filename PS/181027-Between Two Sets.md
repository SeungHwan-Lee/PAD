# [Between Two Sets](https://www.hackerrank.com/challenges/between-two-sets/problem)
## Problem
```
문제가 설명이 이상한데 요약하면
b의 정수들 중에서 균등하게 나울수있는 수를 구한다 그렇기 때문에 b의 최소값보다 이하다
그리고 구한 수를 a의 정수들로 균등하게 나눌수 있는 개수를 구한다
```

## solve - javascript
```javascript
function getTotalX(a, b) {
    let start = getMinMax('max', a);
    let end = getMinMax('min', b);
    let count = 0;
    let check = false;
    for(let i=start; i<=end; i++) {
        check = false;
        for(let num of b) {
            if(num%i != 0) {
                check = false;
                break;
            }else {
                for(let num2 of a) {
                    if(i%num2 != 0) {
                        check = false;
                        break;
                    }else {
                        check = true;
                    }
                }
            }
        }
        if(check) {
            count++;
        }
    }
    return count;
}

function getMinMax(type, arr) {
    let rs = null;
    switch(type) {
        case 'min':
            rs = Number.MAX_SAFE_INTEGER;
            for(let num of arr) {
                if(rs > num) rs = num;
            }
            break;
        case 'max':
            rs = Number.MIN_SAFE_INTEGER;
            for(let num of arr) {
                if(rs < num) rs = num;
            }
            break;
    }
    return rs;
}
```
