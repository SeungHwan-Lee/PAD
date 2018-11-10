# [Designer PDF Viewer](https://www.hackerrank.com/challenges/designer-pdf-viewer/problem)
## Problem
```
word.length * maxHeight
```

## solve - javascript
```javascript
function designerPdfViewer(h, word) {
    let max = 0;
    for(let c of word) {
        let height = h[c.charCodeAt(0)-97];
        if(max < height) max = height;
    }
    return max * word.length;
}
```
