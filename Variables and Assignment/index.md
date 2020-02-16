# Variables and Assignment

## These are JavaScript's main ways of declaring variables

- let declares mutable variables
- const declares constants (immutable variables)

## let

### variables declared via let are **mutable**

```javascript
let i;
i = 2;
i = i + 1;
// you may also assign and declare at the same time.
let i = 1;
```

## const

### variables declared via const must be initialized immediately

> In JavaScript, const only means that the binding (the association between variable name and variable value) is immutable. The value itself may be mutable, like obj in the following example.
> [Source: Dr. Axel Rauschmayer: JavaScript for impatient programmers](https://exploringjs.com/impatient-js/)

```javascript
const i; // throws an error
const i = 2; // initialized immediately
```

---

## The scope of a variable

The scope of a variable is the region of a program where it can be accessed. Consider the following code:

```javascript
{
  // // Scope A. Accessible: x
  const x = 0;
  assert.equal(x, 0);
  {
    // Scope B. Accessible: x, y
    const y = 1;
    assert.equal(x, 0);
    assert.equal(y, 1);
    {
      // Scope C. Accessible: x, y, z
      const z = 2;
      assert.equal(x, 0);
      assert.equal(y, 1);
      assert.equal(z, 2);
    }
  }
}
// Outside. Not accessible: x, y, z
```

- Scope A is the (direct) scope of x
- Scopes B and C are inner scopes of A
- Scope A is an _outer scope_ of scope B and C

It is important to remember that in this example, each variable is accessible
in its direct scope and all scopres nested within that scope.

The variables declared via const and let are called _blocked scoped_ because their scopes are always the innermost surrounding blocks.
