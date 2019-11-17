# 3: Functions

A function definition is a regular binding/variable where the value is a function.

```JavaScript
const square = function(x) {
  return x * x;
};
```

functions can also be declared using _declaration notation_:

```JavaScript
function square(x) {
  return x * x;
}
```

functions declared with declaration notation are _hoisted_ to the beginning of the current scope; This means that you can call a function declared in this way before it is defined.

```JavaScript
console.log(square(2))

function square(x) {
  return x * x;
}

// -> 4
```

**ES6 Arrow functions**

```JavaScript
// These are equivalent
const square = (x) => { return x * x; };
const square = x => x * x; // implicit return
```

**Optional Arguments:**

If you pass more arguments to a function than it has parameters, the extra arguments will simply be ignored. If you pass too few arguments, then `undefined` will be passed to the remaining parameters.

Default values can be assigned for parameters using `=`

```JavaScript
function square(x=1) {
  return x * x;
}

square();

// -> 1
```

**Recursion:** Loops are generally faster than recursive functions. Loops are also easier to understand in my opinion.

---

## _Exercises_

1. **Minimum**

> Write a function min that takes two arguments and returns their minimum.

```JavaScript
function min(a, b) {
  return Math.min(a, b)
}
```

2. **Recursion**

> We’ve seen that % (the remainder operator) can be used to test whether a number is even or odd by using % 2 to see whether it’s divisible by two. Here’s another way to define whether a positive whole number is even or odd:
>
> - Zero is even.
> - One is odd.
> - For any other number N, its evenness is the same as N - 2.
>
>   Define a recursive function `isEven` corresponding to this description. The function should accept a single parameter (a positive, whole number) and return a Boolean.
>
> Test it on 50 and 75. See how it behaves on -1. Why? Can you think of a way to fix this?

```JavaScript
function isEven(num) {
  if (num === 0) return true;
  else if (num === 1) return false;
  else return isEven(num - 2)
}

console.log(isEven(50));
// → true
console.log(isEven(75));
// → false
console.log(isEven(-1));
// → ??

/**
 * When called on -1 you get a stack overflow error.
 * To solve this, convert negative numbers to positive numbers first.
 */

 function isEven(num) {
  if (num < 0) {
    num = num * -1
  }
  if (num === 0) return true;
  else if (num === 1) return false;
  else return isEven(num - 2)
}

console.log(isEven(50));
// → true
console.log(isEven(75));
// → false
console.log(isEven(-1));
// → false
```

3. **Bean Counting**

> Write a function countBs that takes a string as its only argument and returns a number that indicates how many uppercase “B” characters there are in the string.

```JavaScript
function countBs(text) {
  let count = 0;
  for (let i = 0; i < text.length; i++) {
    if (text[i] === 'B'){
      count++
    }
  }
  return count;
}
```

> Next, write a function called countChar that behaves like countBs, except it takes a second argument that indicates the character that is to be counted (rather than counting only uppercase “B” characters). Rewrite countBs to make use of this new function.

```JavaScript
function countChar(text, char) {
  let count = 0;
  for (let i = 0; i < text.length; i++) {
    if (text[i] === char){
      count++
    }
  }
  return count;
}
```
