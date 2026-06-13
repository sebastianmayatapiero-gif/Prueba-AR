# Silla en tu espacio — Experiencia WebAR

Página de realidad aumentada para la clase **"Diseño de experiencias interactivas: del contenido a la experiencia"**. Sin instalación de apps: funciona desde el navegador del teléfono (Android usa Scene Viewer; iPhone usa Quick Look, con USDZ generado automáticamente).

## Contenido de la carpeta

| Archivo | Qué es |
|---|---|
| `index.html` | La página completa (visor 3D + botón AR + instrucciones) |
| `model-viewer.min.js` | Librería de Google incluida localmente (no depende de un CDN) |
| `silla.glb` | Modelo provisional de silla de bambú (28 KB, escala real, origen en la base) |
| `make_silla.py` | Script que generó el modelo provisional (solo referencia, no se sube) |

## Publicar en GitHub Pages (una sola vez)

1. Entra a github.com e inicia sesión (o crea una cuenta).
2. Crea un repositorio nuevo, **público**, llamado por ejemplo `silla-ar`.
3. Botón **Add file → Upload files** y sube estos 3 archivos: `index.html`, `model-viewer.min.js`, `silla.glb`. Confirma con **Commit changes**.
4. Ve a **Settings → Pages**. En "Source" elige **Deploy from a branch**, rama `main`, carpeta `/ (root)`. Guarda.
5. Espera 1–3 minutos. Tu URL será: `https://TUUSUARIO.github.io/silla-ar/`

## Reemplazar por la silla real

1. En Blender: escala real en metros, origen en la base de las patas (centrado), transformaciones aplicadas (Ctrl+A).
2. Exporta como glTF 2.0 en formato `.glb`, con el nombre exacto **`silla.glb`** (texturas máx. 2048 px; ideal < 10 MB).
3. En el repositorio, sube el nuevo `silla.glb` (GitHub pregunta si quieres reemplazarlo: sí). La página se actualiza sola.

> Si en iPhone los materiales se ven mal (la conversión automática a USDZ a veces los degrada), genera un `silla.usdz` con Reality Converter y agrega `ios-src="silla.usdz"` dentro de la etiqueta `<model-viewer>` en `index.html`.

## Generar el QR

1. Abre tu URL en Chrome → botón compartir → **Crear código QR**, o usa cualquier generador de QR.
2. Crea también una **URL corta** (Bitly o similar) para dictarla en voz alta en Zoom como respaldo.

## Lista de pruebas antes de la clase

- [ ] Android: escanear QR → "Ver en tu espacio" → la silla se ancla al piso a tamaño real
- [ ] iPhone: mismo flujo (verificar que los materiales se vean bien)
- [ ] Computador: la página muestra el visor 3D rotable con el mouse
- [ ] Probar con poca luz y sobre piso liso (si el tracking falla, indicar en clase buscar piso con textura)
- [ ] Grabar video de respaldo de 60 segundos del flujo completo
