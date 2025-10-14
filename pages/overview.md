---
title: "Cartolina – 3D terrain cartography for the web"
permalink: /
layout: single
toc: false
sidebar:
  nav: main
header:
  overlay_filter: 0
  
description: "cartolina is an experimental software stack for a web-based 3D cartographic
  terrain representation.  It consists of a frontend JS library and a C++ backend tile server."
---

<!-- ![Water speculars](/assets/images/water-speculars-narrow.jpg) -->

# Cartolina — 3D terrain cartography for the web

`cartolina` is an experimental software stack for a web-based 3D cartographic
terrain representation.  It consists of `cartolina-js`, a frontend
library, and `cartolina-tileserver`, a backend tile server.

## Quickstart

<div id="map" style="height:400px"></div>
<script type="module">
import { map as createMap } from '{{ site.cartolina_js.esm_library }}';

let map = createMap({
    container: 'map',
    style: '/assets/styles/quickstart.json?',
    position: ['obj', -118.302, 36.560, 'fix', 3313, -133, -25, 0.00, 33347,
    45], 
    options: {
	controlFullscreen: true
    }
  });
  
</script>

<p/>

```html
<div id="map"></div>
<script type="module">
import { map as createMap } from '{{ site.cartolina_js.esm_library }}';

let map = createMap({
    container: 'map',
    style: '{{ site.url }}/assets/styles/quickstart.json',
    position: ['obj', -118.302, 36.560, 'fix', 3313, -133, -25, 0.00, 33347, 45]
  });

</script>
```

## Features

- interactive cartographic renditions of DEMs (digital elevation models) at arbitrary resolution and scale

- hillshading based on a native lighting model

- scale-dependent vertical exaggeration 

- bump-mapping based on satelitte or aerial imagery

- background haze and foreground shadows

- sun glints based on land-cover classifications

- seamless support for high-latitude and polar regions

- no inherent dateline or polar-cap issues

- arbitrary frames of reference, including extra-terrestrial bodies for planetary science

- point labels with well defined visual hierarchy 



## Components

<a href="https://github.com/cartolinadev/cartolina-js" target="_blank" rel="noopener">**cartolina-js**</a>
: is a frontend rendering library, written in WebGL2, JavaScript and TypeScript.

<a href="https://github.com/cartolinadev/cartolina-tileserver" target="_blank" rel="noopener">**cartolina-tileserver**</a> 
: is a Unix server deamon, written in C++, which processes geospatial data and streams them
over the network in formats suitable for rendering by Cartolina JS. 

You can find more information about the two components in their
corresponding GitHub repositories (follow the links above).

## License

`cartolina` is open source under a permissive BSD 2-clause license.

The tile server resources hosted at `cdn.tspl.re` and used throught the examples 
on this  website are free to use for development and evaluation. Contact me for any kind 
of production or commercial use. 

