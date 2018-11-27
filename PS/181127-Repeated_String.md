# [Repeated String](https://www.hackerrank.com/challenges/repeated-string/problem)
## Problem
```
s를 길이 n만큼 반복했을때 'a'문자 갯수
```

## solve - java
```java
static long repeatedString(String s, long n) {
    int len = s.length();
    char target = 'a';
    int count = 0;
    for(char c : s.toCharArray()) {
        if(target == c) count++;
    }
    long share = n/len;
    long remainder = n%len;
    long result = share * count;

    if(remainder != 0) {
        for(int i=0; i<remainder; i++) {
            if(target == s.charAt(i)) result++;
        }
    }
    
    return result;
}
```
