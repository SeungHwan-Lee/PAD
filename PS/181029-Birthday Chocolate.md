# [Birthday Chocolate](https://www.hackerrank.com/challenges/the-birthday-bar/problem)
## Problem
```
m번의 만큼 연속적으로 더해서 d와 같을 경우 카운트 반환
```

## solve - javascript
```javascript
function birthday(s, d, m) {
    let sum = 0;
    let count = 0;
    for(let i=0; i<s.length; i++) {
        sum = 0;
        for(let j=i; j<i+m; j++) sum += s[j];
        if(sum === d) count++;
    }
    return count;
}
```
