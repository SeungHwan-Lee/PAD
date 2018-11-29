# [Equalize the Array](https://www.hackerrank.com/challenges/equality-in-a-array/problem)
## Problem
```
최대점프 n+2, 번개시 n+1
```

## solve - java
```java
    static int equalizeArray(int[] arr) {
        Map<Integer, Integer> map = new HashMap<>();
        int max = 1;
        int maxKey = arr[0];
        for(int i=0; i<arr.length; i++) {
            if(map.containsKey(arr[i])) {
                int temp = map.get(arr[i])+1;
                map.put(arr[i], temp);
                if(max < temp) {
                    max = temp;
                    maxKey = arr[i];
                }
            }else {
                map.put(arr[i], 1);
            }
        }
        int count = 0;
        Set key = map.keySet();
        for(Iterator iterator = key.iterator(); iterator.hasNext();) {
            int keyName = (int)iterator.next();
            if(maxKey != keyName) count += map.get(keyName);
        }
        return count;
    }
```
