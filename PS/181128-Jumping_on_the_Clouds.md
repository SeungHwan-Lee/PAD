# [Jumping on the Clouds](https://www.hackerrank.com/challenges/jumping-on-the-clouds/problem)
## Problem
```
최대점프 n+2, 번개시 n+1
```

## solve - java
```java
    static int jumpingOnClouds(int[] c) {
        int count = -1;
        int jump = 1;
        for(int i=0; i<c.length; i+=jump, count++) {
            jump = 1;
            if(i+2 < c.length && c[i+2] != 1) jump++;
        }
        return count;
    }
```
