# 2: Program Structure

**Variables**

```JavaScript
let variable;
variable = 12
```

- `const` defines a _constant_, which cannot be reassigned.

> In browsers, the JavaScript console can be launched with `F12`

---

## _Exercises_

1. **Looping a triangle:**

```JavaScript
for (let row = 0; row < 7; row++) {
    let blocks = "#"
    for (let block = 0; block < row; block++) {
        blocks += "#"
    }
    console.log(blocks)
}
```

2. **FizzBuzz**

```JavaScript
for (let i = 1; i <= 100; i++) {
	if (i % 3 === 0 && i % 5 === 0) {
		console.log("FizzBuzz")
	} else if (i % 3 === 0) {
		console.log("Fizz")
	} else if (i % 5 === 0) {
		console.log("Buzz")
	} else {
		console.log(i)
	}
}
```

3. **Chessboard**

```JavaScript
let size = 8;

for (let row=0; row<size; row++) {
  let rowString = ""
  let char = "#"
  if (row % 2 === 0) {
    char = " "
  }
  for (let col=0; col<size; col++) {
    rowString += char;
    char === " " ? char = "#" : char = " "
  }
  console.log(rowString);
}
```
