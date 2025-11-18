---
title: Terrain with satellite imagery and lettering
permalink: /examples/terrain-satellite-imagery-and-lettering
layout: single
sidebar:
  nav: main   
---

This example provides a planet-wide visualization of lorem ipsum dolor sit
amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
labore et dolore magna aliqua.  Ut enim ad minim veniam, quis nostrud
exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.  Duis
aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu
fugiat nulla pariatur.  Excepteur sint occaecat cupidatat non proident, sunt
in culpa qui officia deserunt mollit anim id est laborum.

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
