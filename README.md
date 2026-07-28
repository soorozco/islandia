# Bitácora Viaje Islandia + Países Bajos 2026

Sitio de la familia Orozco Vela para el viaje del 17 al 31 de octubre de 2026.
Portada con cuenta regresiva, ruta con mapa animado, los 15 días, hoteles,
lugares (con fotos de Wikimedia e historia de Wikipedia), maleta, ropa, idioma
e infografías de la geología de Islandia.

**En vivo:** https://soorozco.github.io/islandia/

## Cómo correrlo en local

Es un sitio estático; hay que servirlo por HTTP (no abrir con `file://`, porque
`places.js`, el mapa y los componentes se cargan por red):

```bash
python3 -m http.server 8000
# abrir http://localhost:8000/
```

## Estructura

| Archivo | Qué es |
| --- | --- |
| `index.html` | Página principal. |
| `Lugar.dc.html` | Ficha de un lugar (sola con `?id=<slug>` o como overlay). |
| `SplitFlap.dc.html` | Relojes tipo split-flap de la sección Ruta. |
| `PackList.dc.html` | Columna de la lista de maleta (checkboxes en `localStorage`). |
| `InfoBlock.dc.html` | Bloques de infografía con diagramas SVG. |
| `places.js` | Datos de los lugares del viaje. |
| `route-map.html` | Mapa animado del vuelo (d3 + world-atlas). |
| `support.js` | Runtime de los archivos `.dc.html`. No editar. |
| `_ds/…/styles.css` | Sistema de diseño (tokens de color, tipografía). |
| `infografias/` | Infografías de géiseres, auroras, glaciares, arena negra y volcanes. |

Con internet se usan: d3 + topojson + world-atlas (mapa) y las APIs de
Wikipedia / Wikimedia Commons (historia y fotos de cada lugar). Todo lo demás es local.
