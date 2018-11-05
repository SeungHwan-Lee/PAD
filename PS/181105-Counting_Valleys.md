# [Counting Valleys](https://www.hackerrank.com/challenges/counting-valleys/problem)
## Problem
```
계곡에 들어갔다 다시나왔을때 카운트
```

## solve - javascript
```javascript
function countingValleys(n, s) {
    const stage = s.split('');
    let step = 0;
    let count = 0;
    let isDown = false;
    
    for(let i=0; i<n; i++) {
        if(stage[i] == 'U') step++;
        else step--;
        
        if(step < 0) isDown = true;
        
        if(step == 0 && isDown) {
            isDown = false;
            count++;
        }
    }

    return count;
}
```
