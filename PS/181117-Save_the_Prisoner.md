# [Save the Prisoner](https://www.hackerrank.com/challenges/save-the-prisoner/problem)
## Problem
```

```

## solve - javascript
```javascript
function saveThePrisoner(n, m, s) {
    const a = s+m-1;   
    if(a>n){
        if(a%n==0) return n;
        return a%n;
    }
    return a;
}
```
