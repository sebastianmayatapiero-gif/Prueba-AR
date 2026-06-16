# Cómo agregar la animación de ensamblaje (nivel reflexivo) desde Blender

La app ya está lista con los tres niveles. El único elemento que requiere tu trabajo en
Blender es la **animación de ensamblaje/desensamblaje** de la silla, que enriquece el nivel
reflexivo (mostrar cómo se arma la pieza). Aquí está el flujo para que la integres sin tocar código.

## Qué hace la app hoy

- **Visceral:** la silla anclada a tamaño real en AR. (Listo)
- **Conductual:** girar/escalar + hotspots numerados que mueven la cámara a cada parte. (Listo)
- **Reflexivo:** hotspot que abre un panel con el origen del taller. (Listo)
- **Reflexivo +animación (TU PARTE):** que al tocar un punto, las cañas se separen mostrando el ensamblaje.

## Pasos en Blender

1. Abre tu modelo real de la silla (o el `silla.glb` provisional, importándolo).
2. Crea una animación donde las partes se separen y vuelvan a unirse (un "exploded view"):
   - Selecciona grupos de piezas (patas, asiento, respaldo).
   - En el frame 0, todo ensamblado. En el frame ~60, las piezas separadas. Inserta keyframes (tecla I → Location).
   - Nombra la acción/animación, por ejemplo `Ensamblaje`.
3. Exporta como glTF 2.0 (.glb) con la opción **"Animation"** activada:
   - File → Export → glTF 2.0
   - En el panel derecho, sección **Animation**, marca "Animations".
   - Guarda como **`silla.glb`** (reemplazando el de la carpeta).

## Activar la animación en la app

La app ya tiene el "enganche" preparado. Si tu GLB incluye una animación llamada `Ensamblaje`,
solo agrega este atributo a la etiqueta `<model-viewer>` en `index.html`:

```
animation-name="Ensamblaje"
```

Y para que se dispare al tocar el hotspot del nivel reflexivo, busca en el `<script>` el bloque
`if(n===3){ panel.classList.add('show'); }` y reemplázalo por:

```javascript
if(n===3){
  panel.classList.add('show');
  mv.animationName='Ensamblaje';
  mv.currentTime=0;
  mv.play({repetitions:1});
}
```

Eso es todo. La cámara, los hotspots y el panel ya funcionan; solo le sumas el movimiento de las piezas.

## Nota sobre AR

Recuerda: los hotspots y paneles **no se muestran dentro del modo AR** (limitación de model-viewer).
Por eso, para grabar los clips de los niveles conductual y reflexivo, hazlo en el **visor 3D**
(antes de tocar "Ver en tu espacio"). El clip visceral sí grábalo en modo AR real, anclando la silla.

## Cómo grabar los tres clips para la actividad

- **Visceral:** modo AR, ancla la silla, grábala apareciendo y a tamaño real. (Grabación de pantalla del teléfono)
- **Conductual:** visor 3D, gira la silla y toca los hotspots numerados. (Grabación de pantalla)
- **Reflexivo:** visor 3D, nivel reflexivo, toca el punto y que aparezca el panel (+ la animación si la agregaste).

Luego conviertes cada grabación a GIF (o las dejas como video corto en la diapositiva).
