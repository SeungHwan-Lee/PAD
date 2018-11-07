# [Picking Numbers](https://www.hackerrank.com/challenges/picking-numbers/problem)
## Problem
```
주어진 정수배열에 숫자갯수가 인접한 n,n+1 or n,n-1 이내에 가장 갯수가 많은 조합
```
프록시 꿀인듯...
## solve - javascript
```javascript
function pickingNumbers(a) {
    const map = new Proxy({},{
        get(target, key) {
            return target[key] || 0;
        }
    });
    for(let num of a) map[num]++;
    let max = 0;
    for(let num of a) {
        let up = map[num]+map[Number(num)+1];
        let down = map[num]+map[num-1];
        if(max < up) max = up;
        if(max < down) max = down;
    }
    return max;
}
```
