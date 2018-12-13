# [Beautiful Triplets](https://www.hackerrank.com/challenges/beautiful-triplets/problem)
## Problem
```

```

## solve - javascript
```javascript
function beautifulTriplets(d, arr) {
    let cnt = 0;
    for (let i = 0; i < arr.length; i++) {
        for (let j = i + 1; j < arr.length; j++) {
            if ((arr[j] - arr[i]) == d) {
                for (let k = j + 1; k < arr.length; k++)
                    if ((arr[k] - arr[j]) == d) cnt++;
            }
        }
    }
    return cnt;
}
```
