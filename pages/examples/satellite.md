---
title: Terrain with satellite imagery and lettering
permalink: /examples/terrain-satellite-imagery-and-lettering
layout: single
sidebar:
  nav: main   
---

This example provides a global, interactive cartographic rendering of
Johnathan de Ferranti’s <a href="https://viewfinderpanoramas.org/"
target="_blank" rel="noopener">Viewfinder Panoramas 90&nbsp;m DEM</a>,
draped with a <a href="https://s2maps.eu/" target="_blank"
rel="noopener">10&nbsp;m global true-color mosaic</a> created from ESA
Sentinel-2 data by EOX IT Services GmbH.

Vertical exaggeration is scale- and elevation-dependent, varying from 1.3 in
close-up views of low-lying areas to 16 in planet-wide views.  Default
settings are used for the physical atmosphere.  The satellite layer is
slightly lightened relative to the darker original to accentuate the impact
of relief shading.  Sun glints on ice and water are based on <a
href="https://esa-worldcover.org/" target="_blank" rel="noopener">ESA
worldcover</a>.

Peak labels are served live from <a href="https://openfreemap.org/"
target="_blank" rel="noopener">OpenFreeMap</a>, with the original tiles
enhanced in real time by [cartolina-tileserver](/#components) to provide
topographic-prominence data, which is used to generate the final visual
hierarchy for each view.  Finally, [cartolina-js](/#components) AST (Abstract Syntax Tree)
stylesheet is used to provide a visual style for the labels.

<div id="map" style="height:450px"></div>
<script type="module">
import { map as createMap } from '{{ site.cartolina_js.esm_library }}';

let map = createMap({
    container: 'map',
    style: '/assets/styles/satellite.json',
    position: ["obj", 8.1452, 46.5512, "float", 0, -51.56, -69.83, 0, 36700, 30],
    options: {
	    controlFullscreen: true
    }
  });
  
</script>

<p/>
