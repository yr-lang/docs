## Usage

Yr can be used either via npm (recommended for projects and tooling) or directly in the browser via a script tag.

---

### Using Yr with npm

Install Yr as a dependency:

```
npm install yr
```

Then import it in your project:

```
import yr from "yr-lang"

// or, if using CommonJS
const yr = require("yr-lang")
```

Basic usage example:

```
const code =
  "><\n" +
  "  _n" +
  "    Hello Yr\n"

const result = yr.parse(code)
console.log(result)
```

You can pass configuration options as the second argument:

```
yr.parse(code, {
  sections: {
    // custom section handlers
  }
})
```

---

### Using Yr in the Browser (CDN)

You can also use Yr directly in the browser without a build step.

```
<script src="https://cdn.jsdelivr.net/npm/yr-lang/dist/yr.min.js"></script>
<script>
  const code =
    "><\n" +
    "  _n" +
    "    Hello Yr\n"

  const output = yr(code)
  console.log(output)
</script>
```

When loaded via script tag, Yr is exposed globally as:

```
window.yr
```

---

### When to use each approach

npm
Use if you are building tools, CLIs, frameworks, or applications.

script tag
Use for quick demos, playgrounds, static sites, or experiments.
