# Babel Minify for loop bug

Run `npm run build` to produce the output file, `out.js`.

In it you will find the problematic section:

```js
const c = /* ... */,
  d = c.length;
let g = "";
for (let d, h = 0; h < d; h++) // <--- Notice how the initializer have `let d`, and the condition `h < d`
  if (d = c[h], 128 > d) g += b(d)
  /* ... */
```
