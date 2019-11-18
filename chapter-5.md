# 5: Higher-Order Functions

**Higher-order functions** - or, _callback functions_ - are functions that operate on other functions.
Remember that functions are just values in bindings

```JavaScript
const binding = function(x) {
  return x
}
```

```JavaScript
["a", "b"].forEach(letter => console.log(letter))
// -> a
// -> b
```

```JavaScript
const square = function(x) {
  return x * x
}

const higherOrder = function(num, callback) {
  return callback(num)
}

// pass square function as argument to higherOrder function
console.log(higherOrder(2, square))
// -> 4
```

_control flow:_

```JavaScript
const square = (x) => {
  console.log("--square")
  return x * x
}

const higherOrder = (num, callback) => {
  console.log("--higherOrder")
  return callback(num) // callback gets invoked here
}

console.log(higherOrder(4, square))
// -> --higherOrder
// -> --square
// -> 16
```
