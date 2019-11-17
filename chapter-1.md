# 1: Values, Types, and Operators

**[Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)**: No distinction between floats and ints.

**Binary Operators:** operate on two values
```
+ * - / %
```
 
**Special Numbers:**

* `Infinity` and `-Infinity`
* `NaN`

**Strings**

```
'string' "string" `string`
```

* `\n` means new line
* `\t` means tab

back-tick string = template literals:
```JavaScript
`half of 50 is ${50 / 2}`
// -> half of 50 is 25
```

**Unary Operators** operate on a single value

```JavaScript
console.log(typeof 4.5)
// -> number

console.log(typeof "x")
// -> string
```

**Boolean values**: `true` and `false`

**Logical Operators:**

* `&&` and
* `||` or
* `!` not

**Ternary/Conditional Operator** operates on three values

```JavaScript
console.log(true ? 1 : 0)
// -> 1
console.log(false ? 1 : 0)
// -> 0
```

**Empty Values:** `null` and `undefined` represent a lack of *meaningful value*.

**Comparison Operators:**

```JavaScript
// strict comparison
a === b
a !== b

// converts type before comparing
a == b
a != b
```

> [BEWARE! Type Coercion:](https://www.youtube.com/watch?v=C5ZVC4HHgIg)
> 
> when using `==` and `!=`, JavaScript will attempt to convert one of the operands to an 'equivalent type' to the other operand. Thus, `'1' == 1 // -> true`, despite one being a number and the other being a string.

## Short-circuiting logical operators

`||` will attempt to convert the left-hand value to a boolean before evaluation, and will return either the *original* left-hand value, or the right-hand value. You can use this to provide a *default value* that will be returned if the first value evaluates as `false` or empty(`null` or `undefined`).

`&&` will return the left-hand value if it evaluates to false when converted to a boolean, and will return the right-hand value if the left-hand value evaluates to true.
