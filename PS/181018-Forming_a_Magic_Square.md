# [Forming a Magic Square](https://www.hackerrank.com/challenges/magic-square-forming/problem)
## Problem
```
주어진 배열에서 최소 변경 마방진 구하기
```

## solve - javascript
```javascript
const SQUARE_LEN = 3; // 3*3
const MAGIC_LEN = 8; // magicList.length
const ROTATION_NUM = 4;
// 3*3에서 정답은 이배열이 전부 회전중복값 제외하고
const magicList = [
    [[8, 1, 6], [3, 5, 7], [4, 9, 2]],
    [[6, 1, 8], [7, 5, 3], [2, 9, 4]],
    [[4, 9, 2], [3, 5, 7], [8, 1, 6]],
    [[2, 9, 4], [7, 5, 3], [6, 1, 8]], 
    [[8, 3, 4], [1, 5, 9], [6, 7, 2]],
    [[4, 3, 8], [9, 5, 1], [2, 7, 6]], 
    [[6, 7, 2], [1, 5, 9], [8, 3, 4]], 
    [[2, 7, 6], [9, 5, 1], [4, 3, 8]],
];

// Complete the formingMagicSquare function below.
function formingMagicSquare(s) {
    let square;
    let minScore = 999;
    let score;
    for(let i=0; i<MAGIC_LEN; i++) {
        square = magicList[i];
        for(let j=0; j<ROTATION_NUM; j++) {
            score = getScore(s, square);
            if(minScore > score) {
                minScore = score;
            }
            square = squareRotation(square);
        }
    }
    return minScore;
}

// 스코어 반환
function getScore(s, square) {
    let score = 0;
    for(let i=0; i<SQUARE_LEN; i++) {
        for(let j=0; j<SQUARE_LEN; j++) {
            score += Math.abs(s[i][j]-square[i][j]);
        }
    }
    return score;
}

// square 오른쪽 회전
function squareRotation(square) {
    const n = SQUARE_LEN;
    const sRotation = new Array(n);
    // 초기화
    for(let i=0; i<n; i++) {
        sRotation[i] = new Array(n);
    }
    // 회전
    for(let i=0; i<n; i++) {
        for(let j=0,k=n-1; j<n; j++,k--) {
            sRotation[i][j] = square[k][i];
        }
    }
    return sRotation;
}
```
