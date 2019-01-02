# [Maximizing XOR](https://www.hackerrank.com/challenges/maximizing-xor/problem)
## Problem
```

```

## solve - Kotlin
```Kotlin
fun maximizingXor(l: Int, r: Int): Int {
    var max = 0
    var rs = 0
    for(i in l..r) {
        for(j in i..r) {
            rs = i xor j
            if(max < rs) max = rs
        }
    }
    return max
}
```
