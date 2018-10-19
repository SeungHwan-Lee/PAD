# [Climbing the Leaderboard](https://www.hackerrank.com/challenges/climbing-the-leaderboard/problem)
## Problem
```
랭킹구하기
```

## solve - javascript
```
function climbingLeaderboard(scores, alice) {
    const re_scores = Array.from(new Set(scores));
    const result = [];
    
    let len = re_scores.length;
    for(let num of alice) {
        let rank = 0;
        for(let i=len-1; i>=0; i--) {
            if(num < re_scores[i]) {
                rank = i+2;
                break;
            }else {
                rank = i+1;
            }
        }
        len = rank;
        result.push(rank);
    }
        
    return result;
}
```