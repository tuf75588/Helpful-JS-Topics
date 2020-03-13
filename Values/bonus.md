# The operators `typeof` and `instanceof`: what's the type of a value

The two operatorators `typeof` and `instanceof` let you determine what type a given value has

Basic examples:

```javascript
if (typeof x === 'string') {...}
if (instanceof y === Array) {...}
```

How do they differ?

- `typeof` distinguishes the 7 types of the specification (minus one omission, plus one addition) -- more on what this means later!
- `instanceof` test which class created a given value.

The most important detail to remember when deciding which to use is:

**`typeof` is for primitive values and `instanceof` is for objects.**

|         x         | typeof x    |
| :---------------: | ----------- |
|     undefined     | 'undefined' |
|       null        | 'object'    |
|      Boolean      | 'boolean'   |
|      String       | 'string'    |
|      Symbol       | 'symbol'    |
|     Function      | 'function'  |
| All Other Objects | 'object'    |

This is all of the results of `typeof` that somewhat correspond to the 7 types of the language, with there being two differences that are quirks of the JavaScript language.

the two differences are:

- `typeof null === 'object'` this is a bug in the language that will likely never be fixed.
- `typeof Function === 'function' should be 'object' (functions are objects). Introducing a seperate category for functions is confusing

---

## `instanceof`

The answer this operator answers is, has a value `x` been created by a `class c`?

```javascript
const x = y instanceof C; //true or false
```

some simple examples of this in real code

```javascript
(function() {}); // instanceof Function
({}); // instanceof Object
[]; // instanceof Array
```
