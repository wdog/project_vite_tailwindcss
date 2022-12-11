# project_vite_tailwindcss


```bash

npm i -D autoprefixer cssnano postcss postcss-cli tailwindcss gsap vite
npx tailwindcss init -p

```


## tailwindcss.conf.js

```bash
/** @type {import('tailwindcss').Config} */
module.exports = {
  mode: 'jit',
  content: ["./src/**/*.html"],
  theme: {
    extend: {},
    fontFamily: {
      sans: ["'Poppins'", "arial", "sans-serif"],
    },
  },
  plugins: [],
};
```


## packages.json


```bash

  "scripts": {
    "build": "vite build --emptyOutDir --base=./",
    "watch": "vite --host --base=./"
  },

```


## postcss.config.js


```javascript
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
    // cssnano: {}, // minify
  },
};
```

## vite

```bash
mkdir src
vim vite.config.js
```

```bash
module.exports = {
  root: "src",
  build: {
    outDir: "../dist",
  },
};
```


## files in src


```bash

touch src/{index.html,input.css,app.js}
```


* fill index.html with references to app.js as module
* in `app.js` add `include "./input.css"`


## input.css

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## app.js

```bash
import "./input.css";
```

## index.html


```bash
<script type="module" src="./input.js"></script>
```
