---
title: Maplibre GL JS demo
---

## MapLibre GL JS

```html
<link href="https://unpkg.com/maplibre-gl/dist/maplibre-gl.css" rel="stylesheet" />
```

```js
import maplibregl from "npm:maplibre-gl"
let pmtiles = await import("https://cdn.skypack.dev/pmtiles")
maplibregl.addProtocol('pmtiles', (new pmtiles.Protocol()).tile)

const div = display(document.createElement("div"))
div.style = "height: 400px;"

const url = await FileAttachment('data/ua.pmtiles').url()
const style = await FileAttachment('data/style.json').json()
style.sources.ua.tiles[0] = "pmtiles://" + url + "/{z}/{x}/{y}"

const map = new maplibregl.Map({
  container: div,
  style: style
})
map.addControl(new maplibregl.FullscreenControl())
map.addControl(new maplibregl.NavigationControl())

invalidation.then(() => map.remove())
```
