# 4: Data Structures: Objects and Arrays

properties can be accessed using either dot notation or bracket notation:

```JavaScript
value.x
value[x]
```

dot notation uses the _literal name_ of the property. The expression within the brackets is _evaluated_ to get the property name.

**Methods:** properties that contain functions.

**Objects** are arbitrary collections of named _properties_.

You can use the `in` operator to check if a key is in an object, same as in python.

`Object.assign()` copies the properties from one object to a new object.

```JavaScript
let objA = {a: 1, b: 2};
let objB = {}
Object.assign(objB, objA, {b:3, c:4})
console.log(objA)
// -> Object { a: 1, b: 2 }
console.log(objB)
// -> Object { a: 1, b: 3, c: 4 }
```

Arrays are objects where the keys are index numbers.

**Array loops**

```JavaScript
let array = [] // array

for (let i = 0; i < array.length; i++) {
  let element = array[i]
  // do something with element
  console.log(element)
}

// SHORTER SYNTAX:

for (let element of array) {
  // do something with element
  console.log(element)
}
```

**Array destructuring**
assign each value of an array to each value of another array

```JavaScript
let [a, b] = ["cat", "dog", "bird"]
console.log(a)
// -> "cat"
console.log(b)
// -> "dog"
```

**Object destructuring**

```JavaScript
let {name} ={name: "Clem", age: 45}
console.log(name)
// -> "Clem"
```

`JSON.parse` converts a JSON-encoded string to a JavaScript object
`JSON.stringify` converts a JavaScript object to a JSON-encoded string.
