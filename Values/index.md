# Values

- What kind of values does JavaScript have?

---

JavaScript distinguishes two types of values, Primative values and Objects

- There is also an important distinction of objects and instances of class `Object`
- Each instance of `Object` (Array,Map,Set,function) is also an object, but not vice-versa
- However, most objects encountered are instances of `Object`, for example, objects created via object literals

```javascript
const obj = {};
```

---

## Types

The ECMAScript spec formally recognizes 7 types, their names are:

- `undefined`
- `null`
- `boolean`
- `number`
- `string`
- `symbol`
- `object`

## Primatives vs. Objects

The JavaScript specification makes a very important distinction between values

Primative values are the elements of the type:

- null
- boolean
- string
- symbol
- undefined
- number

**ALL** other values are considered to be objects.

---

Primative values are considered to be the atomic building blocks of JavaScript and are assigned by value, when assign to variables or passed into functions as parameters, their contents are copied

It is important to remember that primative values are compared by value. When comparing two primative values, their content is compared.

Consider the following example

```javascript
const a = "a";
const b = "a";
console.log(a === b); // true, same value, same contents
```
