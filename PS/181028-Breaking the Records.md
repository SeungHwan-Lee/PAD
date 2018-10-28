# [Between Two Sets](https://www.hackerrank.com/challenges/between-two-sets/problem)
## Problem
```
첫번째 점수 기준으로 최고와 최저 신기록을 달성한 횟수 출력
```

## solve - javascript
```javascript
function breakingRecords(scores) {
    let max = scores[0];
    let min = scores[0];
    const count = [0, 0];
    
    for(let i=1; i<scores.length; i++) {
        if(max < scores[i]) {
            max = scores[i];
            count[0]++;
        }
        if(min > scores[i]) {
            min = scores[i];
            count[1]++;
        }
    }
    
    return count;
}
```
