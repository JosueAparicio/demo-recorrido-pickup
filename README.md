# Demo: recorrido de carro — Pickup 4x4 2023

Micrositio de demostración para concesionarios y rentadoras de carros en El Salvador. Quien quiere comprar o alquilar el carro lo **recorre completo con el scroll**: lo ve llegar, lo rodea, abre el capó, entra a la cabina y lo ve irse. Tiene modo **venta** y modo **alquiler**, precios y botón de WhatsApp.

**Ver en vivo:** https://josueaparicio.github.io/demo-recorrido-pickup/

## Cómo funciona

- **El scroll mueve el video.** Cada tramo es una secuencia de fotogramas WebP pintada en un `<canvas>`: al bajar el carro avanza y al subir retrocede. No usa `<video>`, porque saltar dentro de un MP4 al ritmo del scroll va a tirones.
- **Tres tramos:** afuera (llega, lateral, palangana), motor y cabina (capó abierto, puerta, volante, pantalla, asientos de atrás) y de regreso (se aleja). Entre tramos hay bandas con los datos clave.
- **Transiciones suaves** entre tomas, ya incluidas en los fotogramas, y scroll con inercia ([Lenis](https://github.com/darkroomengineering/lenis)).
- **Textos** que aparecen y se van en puntos fijos del recorrido (`data-from` / `data-to` de cada `.ov`, de 0 a 1).
- **Carga por prioridad:** primero llega una versión liviana de todo el tramo y después la de alta calidad, empezando por donde va el usuario. Hay una versión para celular vertical (`frames/p`, 608×1080) y otra para pantallas horizontales (`frames/d`, 1280×720).

## Para adaptarlo a un cliente

- **WhatsApp, precios y datos:** al final de `main.js` (`WHATSAPP`, `DATA`). Los textos entre corchetes como `[TU PRECIO]` son para reemplazar.
- **Tomas:** los videos fuente van en `video-src/` (no se suben al repo) y las fotos en `img/`. El orden de las tomas y las transiciones están al inicio de `tools/build_frames.py`. Después de cambiarlas:

  ```
  py -m pip install imageio-ffmpeg pillow
  py tools/build_frames.py
  ```

  Eso regenera `frames/`. Si cambia la duración de las tomas, ajustá los `data-from` / `data-to` de los textos en `index.html`.

Las tomas de esta demo se generaron con IA (videos con Google Flow y Veo 3.1 Lite, a partir de fotos; la foto del motor, con un modelo de imagen).
