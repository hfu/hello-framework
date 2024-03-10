---
title: Leaflet demo
---

## Leaflet

```js
const div = display(document.createElement("div"));
div.style = "height: 400px;";

const map = L.map(div)
  .setView([35, 135], 13);

L.tileLayer("https://tile.openstreetmap.org/{z}/{x}/{y}.png", {
  attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a>'
})
  .addTo(map);

L.marker([35, 135])
  .addTo(map)
  .bindPopup("A nice popup<br> 日本へそ公園")
  .openPopup();
```
