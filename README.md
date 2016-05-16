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

#### Example

```javascript
var worstPossibleExample = eval("[].map.call('Eval', function(x){ return x;}).reverse().join('')");
```
#### Explanation
The eval() function evaluates javascript code dynamically. This leads to a few problems.

1. Using it improperly on the client-side could lead to code injection attacks.
2. As you can see in my example, the code inside the eval can become very hard to read.
3. It could make your code slow.

#### Solutions
Don't use eval :)

## Confusing comparision operator

#### Example

```javascript
",,," == new Array(4)); // true
null == undefined; //true
[] == false; // true
```

#### Explanation
The `==` operator has a few problems.
1. It compares just the values on both sides of the equality.
2. It allows type coercing(implicit type casting).

Now, in the first example we can see both of these problems. 
On the left side we have a string with 3 commas, on the right 
side an initialized Array with 4 positions, which will evaluate 
to [, , ,] and get cast to a String, so the interpreter can compare 
the evalues. That's why it returns true.

#### Solutions
Using the `===` comparison operator.
Because it not only compares values but types.

## Automatic semicolon insertion

#### Example

```javascript
var foo = function () {
	return
	{
		1: 'a'
	}
} // throws a syntax error
```

#### Explanation
#### Solutions

### Implied Global variables

#### Example

```javascript
var foo = function () {
	var localVariable = 'local';
	globalVariable = 'global';
}
foo();
```

#### Explanation
<p>
This has to do with the way JavaScript deals with
the scope chain. When you don't use the `var` keyword,
the interpreter will assume you are referencing a variable.
So, if the interpreter can't find the variable in the inner scope,
it will look for it in the outer scope, and will keep doing it until
it reaches the global scope. If it cannot find the variable at all,
the interpreter will then declare it globally.
</p>

#### Solutions
1. Always use the `var` keyword before declaring variables.
2. Enable the ECMAScript 5 strict mode with: `'use strict';`
at the beginning of a file or function, so globals will throw
a ReferenceError
3. If you are writing a module, put yout code in an [IIFE](https://en.wikipedia.org/wiki/Immediately-invoked_function_expression) or better yet, learn to work with the [Module Pattern](https://addyosmani.com/resources/essentialjsdesignpatterns/book/#modulepatternjavascript).
