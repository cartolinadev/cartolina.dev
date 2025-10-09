---
title: Examples
permalink: /examples/
layout: single
sidebar:
  nav: main   # put the site nav in the left column; remove to hide
---

## Live stub

<div id="example-1">
  <button id="run-demo">Run demo</button>
  <pre id="out">output: (click the button)</pre>
</div>

```js
// Simple hillshade intensity from a normal and light direction
function hillshade(nx, ny, nz, lx = 0.5, ly = 0.5, lz = 0.707) {
  return Math.max(0, nx * lx + ny * ly + nz * lz);
}
```

<script>
document.addEventListener("DOMContentLoaded", () => {
  const btn = document.getElementById("run-demo");
  const out = document.getElementById("out");
  if (btn) btn.onclick = () => { out.textContent = "output: " + Math.random().toFixed(3); };
});
</script>

## Map container

```html
<div id="map" style="width:100%;height:480px;border:1px solid #e5e7eb"></div>
```
