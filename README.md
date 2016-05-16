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

* Why?
