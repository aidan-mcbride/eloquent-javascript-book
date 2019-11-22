# 10: Modules

CommonJS modules:

```JavaScript
const someDependency = require("dependency")
const { functionInDependency } = require("dependency2")

exports.myExport = function(x, y) {
  return [x, y]
}
```

CommonJS modules have been succeeded by ECMAScript modules:

```JavaScript
import someDependency from "dependency"
import { functionInDependency } from "dependency2"

export function myExport(x, y) {
  return [x, y]
}
```

`export default` specifies a default export to import when no specific function is specified(line 1 above: `import someDependency from "dependency"`)

**Bundlers** convert multiple javascript modules into a single file.
**Minifiers** shrink your code by removing comments, white space, etc.
