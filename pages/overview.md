---
title: ""
permalink: /
layout: single
toc: false
sidebar:
  nav: main
---

<!-- ![Water speculars](/assets/images/water-speculars-narrow.jpg) -->

## Quickstart

Cartolina is an experimental software stack for a web-based 3D cartographic
terrain representation. It consists of a backend tile server and a frontend
JavaScript/TypeScript library.

<div id="map" style="height:400px"></div>
<script type="module">
import { map as createMap } from '{{ site.cartolina_js.esm_library }}';

let map_ = createMap({
    container: 'map',
    style: './quickstart.json',
    position: ['obj', -118.302, 36.560, 'fix', 3313, -133, -25, 0.00, 33347, 45]
  });
  
</script>

<p/>

```html
<div id="map"></div>
<script>
let map = cartolina.map({
    container: 'map',
    style: 'https://cartolina.dev/quickstart.json',
    position: ['obj', -118.302, 36.560, 'fix', 3313, -133, -25, 0.00, 33347, 45]
  });
</script>
```

## Features

- interactive cartographic renditions of DEMs in arbitrary resolution and scale

- hillshading based on a native lighting model

- scale-dependent vertical exaggeration 

- support for bump maps based on satelitte or aerial imagery

- background haze and foreground shadows

- sun glints based on landcover classifcations

- seamless support for high-altitude and artcic regions

- arbitrary frames of reference, including extra-terrestrial bodies

- point labels with well defined visual hierarchy 



## Components

## License

Cartolina is open source under the permissive BSD 2-clause license.

Please see the [license section]({{ '/using-cartolina/#license' | relative_url }})
for more information on restrictions on usage of the publicly available tileserver.

