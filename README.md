# `yr` - A Lightweight Multi-Stack Wrapper Language

`yr` is a **domain-specific language (DSL)** designed to streamline multi-stack development projects. Built for frontend, backend, and DevOps workflows, it merges stacks such as HTML, CSS, JS, Bash, and Python into a single cohesive language. It eliminates the need for heavy frameworks and excessive boilerplate by using indentation-based syntax, reusable macros, and modular wrapper files.

Think of `yr` as a way to organize a project file. You still write HTML, CSS, JS, Python, and Bash — you just write them all in the same place, separated by simple markers.

---

## Purpose

The goal of `yr` is to:

- Eliminate repetitive HTML and project boilerplate
- Provide reusable macros and components
- Enable seamless cross-stack scripting and code generation
- Offer a developer-friendly syntax based on indentation and triggers
- Simplify dev workflows across frontend, backend, and DevOps

---

## Input and Output

### Input:

- `.yr` files containing indentation-based syntax, macros, wrappers, scripts, and configuration triggers

### Output:

`yr` can output in three primary formats:

1. **Plain Output (default)**:

   - HTML, CSS, and JS compiled and output as inline or separated files.

2. **Full Project Structure**:

```
projectname/
├─ actions/         # Executable scripts (serve, build, deploy)
│  ├─ serve
│  ├─ build
│  └─ deploy
├─ app/
│  ├─ assets/static/
│  ├─ app.js
│  └─ modules/
├─ config.json
├─ db/
├─ www/             # Compiled HTML, CSS, JS
└─ yr/              # Parsed .yr files
```

3. **JSON Mode** *(optional)*:
   - All parsed data (HTML structure, scripts, styles, macros, references) structured into JSON for advanced programmatic usage.

---

## Usage

Yr can be used either via npm (recommended for projects and tooling) or directly in the browser via a script tag.

### Using Yr with npm

Install Yr as a dependency:

```
npm install @yr-lang/yr
```

Then import it in your project:

```
import yr from "@yr-lang/yr"

// or, if using CommonJS
const yr = require("@yr-lang/yr")
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

### Using Yr in the Browser (CDN)

You can also use Yr directly in the browser without a build step.

```
<script src="https://cdn.jsdelivr.net/npm/yr-lang/dist/yr.min.js"></script>
<script>
  const code =
    "><\n" +
    "  _n" +
    "    Hello Yr\n"

  const output = yr.parse(code)
  console.log(output)
</script>
```

When loaded via script tag, Yr is exposed globally as:

```
window.yr
```

### When to use each approach

* npm
Use if you are building tools, CLIs, frameworks, or applications.

* script tag
Use for quick demos, playgrounds, static sites, or experiments.

---

## License

Read the LICENSE for information on how to use or distribute this software. This license should always be available.
