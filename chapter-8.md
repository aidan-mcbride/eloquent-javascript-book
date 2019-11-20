# 8: Bugs and Errors

you can insert `debugger;` into your code and, when run, your browser will pause at that line and load the debugger in dev tools.

You can construct errors using the `Error` constructor:

```JavaScript
function myFunction(x) {
  if (x) return x;
  throw new Error("Missing argument")
}
```

In JS, catch blocks will catch _all thrown errors_, so you need

You can define new error types that inherit from the base `Error` class, then check for those errors in `catch` blocks:

```JavaScript
class ArgumentError extends Error {}

function myFunction(x) {
  if (x) return x;
  throw new ArgumentError("Missing argument")
}

try {
  myFunction();
} catch (e) {
  if (e instanceof ArgumentError) {
    // do something with this error
    console.error("Missing argument")
  } else {
    throw e;
  }
}
```

This way you can handle expected errors, and unexpected errors are reported normally.
