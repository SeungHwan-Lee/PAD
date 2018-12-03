# [ACM ICPC Team](https://www.hackerrank.com/challenges/acm-icpc-team/problem)
## Problem
```

```

## solve - javascript
```javascript
function acmTeam(topic) {
    let result = [];
    for (let i = 0, index = 0; i < topic.length-1; i++) {
        for (let j = i + 1; j < topic.length; j++ , index++) {
            let temp = topic[i].split('');
            let temp2 = topic[j].split('');
            result[index] = [];
            for (let k = 0; k < temp.length; k++) {
                result[index][k] = Number(temp[k]) + Number(temp2[k]);
            }
        }
    }
    let counts = [];
    let maxCount = 0;
    for (let i = 0; i < result.length; i++) {
        counts[i] = 0;
        for (let j = 0; j < result[i].length; j++) {
            if (result[i][j] != 0) counts[i]++;
        }
        if (maxCount < counts[i]) maxCount = counts[i];
    }
    let count = 0;
    for (let c of counts) {
        if (maxCount == c) count++;
    }
    return [maxCount, count];
}
```
