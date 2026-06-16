# Silla en tu espacio — App WebAR de tres niveles

App de realidad aumentada para la clase. Tres niveles de experiencia (Norman):
- **Visceral**: la silla anclada a tamaño real en AR.
- **Conductual**: girar/escalar + hotspots que inspeccionan cada parte.
- **Reflexivo**: hotspot que abre el panel con el origen del taller.

## Archivos
- `index.html` — la app completa
- `model-viewer.min.js` — librería (local, sin CDN)
- `silla.glb` — modelo (reemplázalo por tu silla real con animación; ver guía)
- `ANIMACION_ENSAMBLAJE.md` — cómo agregar la animación de ensamblaje desde Blender

## Publicar
Sube los archivos al repositorio de GitHub Pages (reemplazando los anteriores).
La URL y el QR siguen siendo los mismos.

## Para la demo en vivo (versión "downgrade")
Para la demostración previa, puedes usar una versión simplificada que solo muestre el nivel
visceral (silla anclada, sin hotspots ni panel). Así el comité vive el "grado cero" y la
actividad posterior revela los tres niveles. Para hacerlo, basta con ocultar el selector de
niveles y dejar fijo el nivel 1 — avísame y te preparo ese index_demo.html aparte.
