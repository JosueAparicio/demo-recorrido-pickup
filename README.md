# Demo: recorrido de carro — Pickup 4x4 2023

Micrositio de demostración para concesionarios y rentadoras de carros en El Salvador: el carro se presenta como un recorrido en una sola página, de afuera hacia adentro, con modo **venta** y modo **alquiler**, precios y botón de WhatsApp.

El recorrido son 9 tomas a pantalla completa, una por pantalla al deslizar. Cinco son **video** (el carro se acerca, la cámara lo acompaña de lado, entra por la puerta, maneja al volante y lo ve alejarse) y se reproducen solas al llegar a cada toma. Las otras cuatro (frente, tablero, asientos traseros y palangana) son fotos con un movimiento de cámara lento. En pantallas anchas cada toma va en un encuadre vertical, con el texto a la izquierda.

**Ver en vivo:** https://josueaparicio.github.io/demo-recorrido-pickup/

## Para adaptarlo a un cliente

Todo está en `index.html`:

- **WhatsApp:** cambiá `var WHATSAPP = '50370000000';` por el número del negocio, con código de país y sin `+` ni espacios.
- **Precios y datos:** reemplazá los textos entre corchetes, como `[TU PRECIO]` o `[PRIMA]`.
- **Videos:** están en `video/` (`01-se-acerca.mp4`, `03-lateral.mp4`, `04-puerta.mp4`, `05-al-volante.mp4`, `09-se-va.mp4`), cada uno con su imagen de portada `.jpg` del mismo nombre. Son verticales 9:16, de 8 segundos, sin audio y de 1 a 1.4 MB cada uno. Para otro carro, reemplazalos con los mismos nombres. Los de esta demo se generaron con IA (Google Flow, Veo 3.1 Lite) a partir de las fotos.
- **Fotos:** están en `img/`, verticales, de 1080 px de ancho. El acercamiento de cada foto se ajusta con `--ox`/`--oy` (punto hacia donde se acerca) y `--z` (cuánto) en su atributo `style`.
- **Venta o alquiler:** los textos de cada modo están en los atributos `data-venta` y `data-alquiler`.

Es un solo archivo HTML más las carpetas de fotos y videos, sin dependencias: se abre con doble clic o se publica en cualquier hosting estático.
