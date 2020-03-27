# The non-values of JavaScript

- The JavaScript langugage has two "non-value" values, they are `undefined` and `null`

In JavaScript, these values are sometimes used interchangebly, how they differ between one another can be a little more subtle and will be the topic of this entry.

At a high level, `undefined` refers to something that is "not initialized" (usually in the context of some variable)

`null` on the other hand refers to the intentional absense of an object value, this is the offical wording the language specification uses when describing it.

In more practical terms, the distinction between the two are usually made this way:

1. `undefined` is the official "non-value" used by the language.
2. `null` means "explicity" switched off and having no meaningful value whatsoever.

Some common occurances of `undefined` you might see when using JavaScript

- Unitialized variables

```javascript
let x;
console.log(x); // undefined
```

- Function parameters omitted when invoking a function

```javascript
function foo(x) {
  return x;
}
console.log(foo()); // undefined
```

- Accessing an object property that does not exist

```javascript
const obj = {};
obj.foo; // undefined
```

- If you dont explicity specify the result via a `return` statement in the body of a function, you will be returned `undefined`

```javascript
function foo(x) {
  console.log(x);
}
foo(3); // undefined, but will log 3
```
