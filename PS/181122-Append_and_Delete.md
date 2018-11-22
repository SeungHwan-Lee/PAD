# [Append and Delete](https://www.hackerrank.com/challenges/append-and-delete/problem)
## Problem
```

```

## solve - javascript
```javascript
function appendAndDelete(s, t, k) {
    let rs = "Yes";
    if (s != k) {
        let count = 0;
        for (let i = 0; i < s.length, i < t.length; i++) {
            if (s[i] == t[i]) count++;
            else break;
        }
        let sLen = s.length - count;
        let tLen = t.length - count;
        if (tLen % 2 != 0 && k%2 == 0) rs = "No";
        else if (k < sLen + tLen) rs = "No";
    }
    return rs;
}
```
