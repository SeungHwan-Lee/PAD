# [Sequence Equation](https://www.hackerrank.com/challenges/permutation-equation/problem)
## Problem
```

```

## solve - javascript
```javascript
function permutationEquation(p) {
    const n = p.length;
    const p_inverse = [];
    const result = [];
    for (let i=1; i<=n; i++) p_inverse[p[i-1]] = i;
    for (let i=1; i<=n; i++) result.push(p_inverse[p_inverse[i]]);
    return result;
}
```
