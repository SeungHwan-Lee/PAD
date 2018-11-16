# [Viral Advertising](https://www.hackerrank.com/challenges/strange-advertising/problem)
## Problem
```
1 day floor(5/2) = people, 2 day floor(people*3/2) = people ... 총 people 합계
```

## solve - javascript
```javascript
function viralAdvertising(n, people) {
    if(n == 0) return 0;
    
    let like = 2;
    if(people) {
        like = Math.floor(people*3/2);
    }else {
        like = Math.floor(5/2);
    }
    
    return like + viralAdvertising(--n, like);
}
```
