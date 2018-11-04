# [Drawing Book](https://www.hackerrank.com/challenges/drawing-book/problem)
## Problem
```
책을 현재페이지에서 오른쪽으로 넘기는게 적은지
처음부터 왼쪽으로 넘기는게 적은지 비교해서 가장 작은 횟수 출력
```

## solve - javascript
```javascript
function pageCount(n, p) {
    return Math.min(Math.floor(p/2), Math.floor(n/2) - Math.floor(p/2));
}
```
