# 6: Object-Oriented Programming

**[Encapsulation:](<https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)>)** bundle data with the methods that operate on that data, and have the methods serve as an interface to the data.

**Methods**

methods are properties in an object to which a function is assigned:

```JavaScript
let rabbit = {
  name: 'roger',
  age: 6,
  speak: function(line) {
    console.log(`the rabbit says '${line}'`)
  }
}

rabbit.speak('words!')
// -> the rabbit says 'words!'
```

the binding **`this`** refers to the object instance on which the method was called:

```JavaScript
function identify() {
  console.log(`This fox is ${this.color}`)
}

let redFox = {
  color: 'red',
  identify: identify
}
let brownFox = {
  color: 'brown',
  identify // same as above
}

redFox.identify()
// -> This fox is red
brownFox.identify()
// -> This fox is brown
```

arrow functions use the `this` from the scope that they are called in, rather than creating their own `this`.

**Object prototypes**

Objects inherit their properties from _prototypes_, which can in turn inherit from other prototypes.

You can create objects from prototypes using `Object.create()`

```JavaScript
let protoFox = {
  color: "brown",
  speak: function(line) { console.log(`The ${this.color} fox says: '${line}'`)}
}

let redFox = Object.create(protoFox);
redFox.color = "red";
redFox.speak("REEEE!");
// -> The red fox says: 'REEEE!'
```

**constructor function:**

```JavaScript
function makeFox(color) {
  let fox = Object.create(protoFox);
  fox.color = color;
  return fox
}
```

If you put the keyword **`new`** in front of a function call, that function will become a **_constructor_**.

## ES6 Class Notation

Less cumbersome way of declaring classes.

```JavaScript
class Dog {
  constructor(isGoodBoy) {
    this.isGoodBoy = isGoodBoy;
  }
  speak() {
    console.log('bark!')
  }
}
```

## Map

JavaScript has a `Map` class that stores a mapping of key-value pairs. If a normal object is used for this, you get problems when the object inherits properties from its prototype:

```JavaScript
let ages = {
  Clem: 24,
  Brandi: 22,
  Leroy: 65
};

console.log("Clem" in ages);
// -> true
console.log("toString" in ages);
// -> true
```

Using [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map) instead:

```JavaScript
/* Maps can be initialized from an iterable */
let ages = new Map([["Clem", 24], ["Brandi", 22]])
ages.set("Leroy", 65)

console.log(ages)
// -> Map(3) { Clem → 24, Brandi → 22, Leroy → 65 }
console.log(ages.get("Clem"))
// -> 24
console.log(ages.has("toString"))
// -> false
```

**Getters** are methods of a class used to retrieve data, which may abstract another method call. Getters are called whenever the property with that name is read:

```JavaScript
let varyingSize = {
  get size() {
    return Math.floor(Math.random() * 100);
  }
};

console.log(varyingSize.size);
// → 73
console.log(varyingSize.size);
// → 49
```

**Setters** correspond to getters, but are called when a property is written to:

```JavaScript
class Temperature {
  constructor(celsius) {
    this.celsius = celsius;
  }
  get fahrenheit() {
    return this.celsius * 1.8 + 32;
  }
  set fahrenheit(value) {
    this.celsius = (value - 32) / 1.8;
  }

  static fromFahrenheit(value) {
    return new Temperature((value - 32) / 1.8);
  }
}

let temp = new Temperature(22);
console.log(temp.fahrenheit);
// → 71.6
temp.fahrenheit = 86;
console.log(temp.celsius);
// → 30
```

Methods with `static` before them are stored on the _constructor_, so you can call that method when instantiating that class:

```JavaScript
Temperature.fromFahrenheit(100)
// -> Object { celsius: 37.77777777777778 }
```

**Inheritance:** Classes can be created from other classes, and inherit all the properies and methods of the base class:

```JavaScript
class Beagle extends Dog {
  //
}
```
