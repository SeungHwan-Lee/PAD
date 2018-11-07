# [Cats and a Mouse](https://www.hackerrank.com/challenges/cats-and-a-mouse/problem)
## Problem
```
고양이 A,B중 먼저 쥐를 잡거나 쥐가 도망가거나
```

## solve - javascript
```javascript
function catAndMouse(x, y, z) {
    const catA = Math.abs(x-z);
    const catB = Math.abs(y-z);
    if(catA == catB) {
        return 'Mouse C';
    }else {
        if(catA > catB) {
            return 'Cat B';
        }else {
            return 'Cat A';
        }
    }
}
```
