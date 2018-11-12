# [Angry Professor](https://www.hackerrank.com/challenges/angry-professor/problem)
## Problem
```

```

## solve - javascript
```javascript
function angryProfessor(k, a) {
    let count = 0;
    for(let n of a) {
        if(n <= 0) count++;
    }
    return count < k ? 'YES' : 'NO';
}
```
