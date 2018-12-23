# [Halloween Sale](https://www.hackerrank.com/challenges/halloween-sale/problem)
## Problem
```

```

## solve - Kotlin
```Kotlin
fun howManyGames(p: Int, d: Int, m: Int, s: Int): Int {
    var count = 0
    var tempS = s
    var tempP = p
    while(tempS >= tempP){
        count++
        tempS -= tempP
        tempP = Math.max(tempP - d, m)
    }
    return count
}
```
