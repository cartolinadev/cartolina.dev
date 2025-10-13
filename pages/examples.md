---
title: Simple terrain with exaggeration, haze and shadows
permalink: /examples/
layout: single
sidebar:
  nav: main   
---


This example provides a planet-wide visualization of Copernicus GLO-30 DEM. It's 
the same configuration as the one used [here](/#quickstart) with a couple of 
distinctions. Vertical exaggeration is set to vary between 1 and 16 according 
to the map scale. The atmospheric visibility is made dependent on 
distance, making the haze more pronounced in close-up views.  

<div id="map" style="height:400px"></div>
<script type="module">
import { map as createMap } from '{{ site.cartolina_js.esm_library }}';

let map = createMap({
    container: 'map',
    style: '/assets/styles/01-simple.json',
    position: ['obj', -123, 47, 'fix', 609.68, 138.46, -4.67, 0, 46453, 25],
    options: {
	    controlFullscreen: true
    }
  });
  
</script>

<p/>
A related example leaves out the illumination altogether, showing just the haze 
and shadows effects.
  
<div id="map2" style="height:400px"></div>
<script type="module">
//import { map as createMap } from '{{ site.cartolina_js.esm_library }}';

let map2 = createMap({
    container: 'map2',
    style: '/assets/styles/01a-simple.json',
    position: ['obj', -123, 47, 'fix', 609.68, 138.46, -4.67, 0, 46453, 25], 
    options: {
	    controlFullscreen: true
    }
  });
  
</script>
