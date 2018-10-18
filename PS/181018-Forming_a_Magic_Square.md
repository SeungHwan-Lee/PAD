# [Forming a Magic Square](https://www.hackerrank.com/challenges/magic-square-forming/problem)
## Problem
```
We define a magic square to be an  matrix of distinct positive integers from  to  where the sum of any row, column, or diagonal of length  is always equal to the same number: the magic constant.

You will be given a  matrix  of integers in the inclusive range . We can convert any digit  to any other digit  in the range  at cost of . Given , convert it into a magic square at minimal cost. Print this cost on a new line.

Note: The resulting magic square must contain distinct integers in the inclusive range .

For example, we start with the following matrix :

5 3 4
1 5 8
6 4 2
We can convert it to the following magic square:

8 3 4
1 5 9
6 7 2
This took three replacements at a cost of .

Function Description

Complete the formingMagicSquare function in the editor below. It should return an integer that represents the minimal total cost of converting the input square to a magic square.

formingMagicSquare has the following parameter(s):

s: a  array of integers
Input Format

Each of the lines contains three space-separated integers of row .

Constraints

Output Format

Print an integer denoting the minimum cost of turning matrix  into a magic square.

Sample Input 0

4 9 2
3 5 7
8 1 5
Sample Output 0

1
Explanation 0

If we change the bottom right value, , from  to  at a cost of ,  becomes a magic square at the minimum possible cost.

Sample Input 1

4 8 2
4 5 7
6 1 6
Sample Output 1

4
Explanation 1

Using 0-based indexing, if we make

-> at a cost of 
-> at a cost of 
-> at a cost of ,
then the total cost will be .
```

## solve - javascript
```
'use strict';

const fs = require('fs');

process.stdin.resume();
process.stdin.setEncoding('utf-8');

let inputString = '';
let currentLine = 0;

process.stdin.on('data', inputStdin => {
    inputString += inputStdin;
});

process.stdin.on('end', function() {
    inputString = inputString.replace(/\s*$/, '')
        .split('\n')
        .map(str => str.replace(/\s*$/, ''));

    main();
});

function readLine() {
    return inputString[currentLine++];
}

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

function main() {
    const ws = fs.createWriteStream(process.env.OUTPUT_PATH);

    let s = Array(3);

    for (let i = 0; i < 3; i++) {
        s[i] = readLine().split(' ').map(sTemp => parseInt(sTemp, 10));
    }

    const result = formingMagicSquare(s);

    ws.write(result + '\n');

    ws.end();
}
```