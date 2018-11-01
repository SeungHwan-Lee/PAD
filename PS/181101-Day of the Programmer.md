# [Day of the Programmer](https://www.hackerrank.com/challenges/day-of-the-programmer/problem)
## Problem
```
윤년계산이 중간에 변한다 1918이상 그레고리력
```

## solve - javascript
```javascript
function dayOfProgrammer(year) {
    return `${getDay(year)}.09.${year}`;
}

function getDay(year){
    const D = 256;
    let d_sum = 0;
    let check = false;
    if(year%4 == 0
       && (year<1918 || year%400 == 0
           || (year%4 == 0 && year%100 != 0))) {
        check = true;
    }
    for(let i=1; i<=8; i++){
        let d = 31;
        switch(i){
            case 2:
                d = 28;
                if(check) d = 29;
                break;                
            case 4:
            case 6:
            case 9:
            case 11:
                d = 30;
                break;
        }
        d_sum += d;
    }
    if(year == 1918) d_sum -= 13;
    return D - d_sum;
}
```
