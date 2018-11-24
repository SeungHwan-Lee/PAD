# [Cut the sticks](https://www.hackerrank.com/challenges/cut-the-sticks/problem)
## Problem
```

```

## solve - javascript
```javascript
function cutTheSticks(arr) {
    const result = [];
    while (true) {
        if (arr.length == 0) break;
        result.push(arr.length);
        let min = Number.MAX_SAFE_INTEGER;
        for (let i = 0; i < arr.length; i++) {
            if (min > arr[i]) min = arr[i];
        }
        for (let i = 0; i < arr.length; i++) {
            arr[i] -= min;
            if (arr[i] == 0) {
                arr.splice(i, 1);
                i--;   
            }
        }
    }
    return result;
}
```
