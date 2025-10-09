---
title: Getting started
permalink: /getting-started/
layout: single
sidebar:
  nav: main   # left column replicates tabs; remove this block to hide sidebar
---

## Install

```bash
npm install @cartolina/core
```

## Minimal init

```html
<div id="map"></div>
<script type="module">
  import { createMap } from "https://cdn.example.com/cartolina.js";
  const map = createMap(document.getElementById("map"), {
    terrain: "dem",
    basemap: "outdoors"
  });
</script>
```
