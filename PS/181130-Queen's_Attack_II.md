# [Queen's Attack II](https://www.hackerrank.com/challenges/queens-attack-2/problem)
## Problem
```
퀸의 공격가능한 경의수
```

## solve - javascript
```javascript
function queensAttack(n, k, r_q, c_q, obstacles) {
    // n 맵크기, k 공격불가 개수, r_q, c_q 퀸위치, obstacles 공격불가 위치
    let l = c_q - 1;
    let r = n - c_q;
    let u = n - r_q;
    let d = r_q - 1;
    let ru = Math.min(u, r);
    let rd = Math.min(r, d);
    let lu = Math.min(l, u);
    let ld = Math.min(l, d);

    for (let o of obstacles) {
        if (o[0] == r_q) {
            if (c_q < o[1]) {
                r -= n - o[1] + 1;
            } else {
                l -= o[1];
            }
        } else if (o[1] == c_q) {
            if (r_q < o[0]) {
                u -= n - o[0] + 1;
            } else {
                d -= o[0];
            }
        } else if (Math.abs(o[0] - r_q) == Math.abs(o[1] - c_q)) {
            if (o[1] > c_q) {
                if (o[0] > r_q) {
                    ru = Math.min(ru, o[1] - c_q - 1);
                } else {
                    rd = Math.min(rd, o[1] - c_q - 1);
                }
            } else {
                if (o[0] > r_q) {
                    lu = Math.min(lu, c_q - 1 - o[1]);
                } else {
                    ld = Math.min(ld, c_q - 1 - o[1]);
                }
            }
        }
    }
    return l + r + u + d + ru + rd + lu + ld;
}
```
