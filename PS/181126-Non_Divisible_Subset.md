# [Non-Divisible Subset](https://www.hackerrank.com/challenges/non-divisible-subset/problem)
## Problem
```
거지같은 문제...
```

## solve - java
```java
static int nonDivisibleSubset(int k, int[] S) {
    int totalPair[][] = new int[k/2][2];
    int nonDivisible = 0;
    int remainders[] = new int[S.length];
    boolean conatinZeroRemainder = false;
    for(int i=1; i<=totalPair.length; i++){
        totalPair[i-1][0] = i;
        totalPair[i-1][1] = k-i;
    }

    for(int i=0; i< S.length; i++){
        remainders[i] = S[i]%k;
        if(remainders[i] == 0) conatinZeroRemainder = true;
    }

    for(int i=0;i<totalPair.length;i++){
        int p1 = totalPair[i][0];
        int p2 = totalPair[i][1];
        int p1C = 0;
        int p2C = 0;
        if(p1 == p2){
            nonDivisible = nonDivisible+1;
            break;
        }
        for(int j=0; j<remainders.length; j++){
            if(p1 == remainders[j]) p1C++;
            if(p2 == remainders[j]) p2C++;
        }

        nonDivisible = nonDivisible + (p1C>p2C ? p1C : p2C);

    }
    if(conatinZeroRemainder){
        return nonDivisible+1;
    }
    return nonDivisible;
}
```
