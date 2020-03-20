# Operators

On the surface, JavaScript operators appear to be the culprits of some of the more strange quirks of the langugage. While that can be the case, they can also become more predictable in their behavior once you know some fundamental concepts about them.

With the following two rules, operators become a bit more easy to understand.

1. Operators coerce their operands to primitive values
2. Most operators only work with primitive values

## Operators coerce their operands to appropriate types

If an operator gets operands that don't have the proper types, it rarely throws an exception. Instead, it _coerces_ (automatically converts) the operands so that it can work with them. Lets look at two examples.

First, the multiplication operator can only work with numbers. Therefore, it converts strings to numbers before computing its result

```javascript
"7" * 3;
// 21
```

Second, the square brackets operator ([]) for accessing properties of an object can only handle strings and symbols. All other values are coerced to a string.

```javascript
const obj = {};
obj["true"] = 123;

// coerce true to the string 'true'
```
