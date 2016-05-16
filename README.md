# Programming Languages Bad Features [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

> Not so Awesome Programming Languages Bad Features

**Table of Contents**

- [JavaScript](#javascript)
- [Python](#python)
- [Ruby](#ruby)
- [Java](#java)
- [PHP](#php)

# JavaScript

## eval()

* Example

```
var worstPossibleExample = eval("[].map.call('Eval', function(x){ return x;}).reverse().join('')");
```
* Explanation

* Why?

## Confusing comparision operator

* Example

```javascript
console.log(",,," == new Array(4)); // true
null == undefined; //true
[] == false
```

* Explanation
<p>
The `==` operator compares just the value on both side
of the equality. Now, in the first example, on the left side
we have a string with 3 commas, on the right side a initialized
Array with 4 positions, which will evaluate to [, , ,] and get cast
to a String, so the interpreter can compare the evalues. That's why
it will return true.
<p>

* How to fix it
<p>
Using the `===` comparison operator.
Because it not only compares values but types
<p>
## Automatic semi-colon insertion

* Example
* Explanation
* How to fix it

### Implied Global variables

* Example
* Explanation
* How to fix it

