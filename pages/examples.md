---
title: Examples
permalink: /examples/
layout: single
sidebar:
  nav: main   # put the site nav in the left column; remove to hide
---

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium
doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore
veritatis et quasi architecto beatae vitae dicta sunt explicabo.  Nemo enim
ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia
consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt.  Neque
porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur,
adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et
dolore magnam aliquam quaerat voluptatem.  Ut enim ad minima veniam, quis
nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid
ex ea commodi consequatur?  Quis autem vel eum iure reprehenderit qui in ea
voluptate velit esse quam nihil molestiae consequatur, vel illum qui dolorem
eum fugiat quo voluptas nulla pariatur?

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
