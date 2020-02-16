# The following is more advanced material for variable declaration and Assignment

## Terminology - Static vs. Dynamic

### These two adjectives describe phenomena in programming languages

- _Static_ means that something is related to source code and can be determined without executing code.
- _Dynamic_ means at runtime.

## Static exmaple

Variable scopes are a static phenomenon. Consider the following example:

```javascript
function f() {
  const x = 3;
}
```

x is _staticly_ scoped. That is, its scope is fixed and doesn't change at runtime.

Variable scopes form a static tree. (via static nesting).

## Dynamic example

Function calls are a dynamic phenomenon. Consider the following code:

```javascript
function g() {}
function h(y) {
  if (Math.random()) g(y); // (A)
}
```

Whether or not the function call in line A happens can only be decided at runtime

Function calls form a dynamic tree (via dynamic calls)

---

## const, let, and the temporal dead zone

The time between entering the scope of a variable, and its executing its declaration is called the _temporal dead zone_ of that variable.

- During this time, the variable is considered _uninitialized_ (as if that were a special value it has).
- If you access an uninitialized variable, you get a `ReferenceError`
- Once you reach the variable declaration, the variable is set to either the value of the initializer (specified via the assignment symbol) or `undefined` - if there is no initializer.

The following code illustrates the temporal dead zone:

```javascript
if (true) {
  // entering scope of `tmp`, TDZ starts
  // `tmp` is uninitialized:
  assert.throws(() => (tmp = "abc"), ReferenceError);
  assert.throws(() => console.log(tmp), ReferenceError);

  let tmp; // TDZ ends
  assert.equal(tmp, undefined);
}
```

The next example shows that the temporal dead zone is truly temporal (related to time)

```javascript
if (true) {
  // entering scope of `myVar`, TDZ starts
  const func = () => {
    console.log(myVar); // executed later
  };

  // We are within the TDZ:
  // Accessing `myVar` causes `ReferenceError`

  let myVar = 3; // TDZ ends
  func(); // OK, called outside TDZ
}
```

Even though func() is located before the declaration of `myVar` and uses that variable, we can call func(). But we have to wait until the temporal dead zone of myVar is over
