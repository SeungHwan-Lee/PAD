# [Time Conversion](https://www.hackerrank.com/challenges/time-conversion/problem)
## Problem
```
정해진 시간 포맷에서 24h로 출력
```

## solve - javascript
```javascript
function timeConversion(s) {
    let result = null;
    const len = s.length;
    const AP = s.substr(len-2, len);
    const dates = s.substr(0, len-2).split(':');
    switch(AP) {
        case 'AM':
            if(dates[0] == '12') dates[0] = '00';
            break;
        case 'PM':
            if(dates[0] != '12') dates[0] = Number(dates[0]) + 12;
            break;
    }
    result = dates.join(':');
    return result;
}
```
