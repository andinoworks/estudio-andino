# Pipeline de producción

Cada video sigue los mismos pasos; casi todos son un comando.

## 1. Guion
Archivo de datos con la voz, la velocidad y una lista de segmentos (`id`, `capítulo`, `texto`).
Las palabras entre asteriscos se resaltan en pantalla. Reglas: datos exactos, autor y año de cada fuente,
números escritos como se dicen, frases cortas.

## 2. Voz
- Voz neural en español (México/Argentina) con velocidad ajustada, o
- voz clonada que corre en la GPU local (modelos abiertos), para memes y edits con más actuación.
Después de generar, un auditor compara el texto con lo que realmente se dijo y detecta tomas truncadas;
las tomas malas se rehacen con otra semilla.

## 3. Línea de tiempo
Se obtiene el cuadro exacto de cada palabra. Las escenas usan esos tiempos: "cuando dice *neutrón*, aparece la estrella".

## 4. Música y efectos
Música generada por código según tempo, tonalidad y estilo, de la duración justa. Efectos de sonido mínimos.

## 5. Escenas
Componentes de React que dibujan cada cuadro:
- gráficos y diagramas en SVG con estilo propio, contadores, citas, fórmulas (KaTeX);
- 3D proyectado en SVG o 3D real con Three.js;
- simulaciones deterministas (mismo resultado en cada render) dibujadas en canvas;
- escenas con física en Blender: objetos con masa real que caen y chocan, personajes con esqueleto que caminan o corren,
  cielo HDRI, polvo y temblor de cámara;
- metraje de archivo de dominio público (NASA, Wikimedia Commons) cuando corresponde.

Para los memes 3D, cada escena se describe como datos (cámara, momentos, etiquetas, estado del mundo) y el sistema
genera los cortes de cámara alineados a las palabras.

## 6. Revisión
- Hojas de contacto con cuadros clave.
- QA de composición (ver [calidad.md](calidad.md)).

## 7. Render
Render en paralelo con codificación por GPU, normalización de volumen a −14 LUFS, look de color opcional y QA del MP4.

## 8. Publicación
Cola con horario: YouTube (largo con capítulos y miniatura, Short con enlace al largo), Facebook (video de página y Reel)
y TikTok espaciado. Cada subida se verifica después.
