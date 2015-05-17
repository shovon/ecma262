# Array.prototype.findLast

A proposal for an ECMAScript native method

## Code

```javascript
// Code largely inspired from prettydiff/ecma262#5623d1a2444543e106e26e11601cb0d2504ab39f

Array.prototype.findLast = function (cb) {
  for (var i = this.length - 1; i >= 0; i--){
    if(cb(this[i], i)) return this[i];
  }
};

// Example
let a = [ "asfd", "qwer", "zxcv", "last Item" ];

a.findLast(function (value) {
  return /x/.test(value);
});
```

## Why we need it

`Array.prototype.find` is used if we want to find the first element that matches a given predicate. However, it will be ideal if we are to have a convenience method that looks for the last element that matches a given predicate.