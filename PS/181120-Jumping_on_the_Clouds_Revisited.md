# [Jumping on the Clouds Revisited](https://www.hackerrank.com/challenges/jumping-on-the-clouds-revisited/problem)
## Problem
```

```

## solve - javascript
```javascript
function jumpingOnClouds(c, k) {
    let energy = 100;
    for (let i = 0; i < c.length; i += k) {
        if (c[i] == 1) energy -= 3;
        else energy--;
    }
    return energy;
}
```
