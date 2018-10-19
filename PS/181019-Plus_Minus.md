# [Plus Minus](https://www.hackerrank.com/challenges/plus-minus/problem)
## Problem
```
배열을 받고 각각의 값을 구한다
양의정수 개수/arr.length
음의정수 개수/arr.length
0의 개수/arr.length
```

## solve - javascript
```
function plusMinus(arr) {
    const len = arr.length;
    const count = [0, 0, 0];
    for(let num of arr) {
        if(num > 0) {
            count[0]++;
        }else if(num < 0) {
            count[1]++;
        }else {
            count[2]++;
        }
    }
    for(let num of count) {
        console.log(num/len);
    }
}
```