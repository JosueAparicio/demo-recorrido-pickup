# Demo: recorrido de carro — Pickup 4x4 2023

Micrositio de demostración para concesionarios y rentadoras de carros en El Salvador: el carro se presenta como un recorrido en una sola página, de afuera hacia adentro, con modo **venta** y modo **alquiler**, precios y botón de WhatsApp.

El recorrido es una sola toma en 9 fotos con movimiento de cámara guiado por el scroll (acercamientos, paneos y alejamientos, con inercia suave). Cada foto tiene su propio movimiento: el carro se acerca, el frente, el lateral, la puerta, al volante, el tablero, los asientos traseros, la palangana y el carro alejándose.

**Ver en vivo:** https://josueaparicio.github.io/demo-recorrido-pickup/

## Para adaptarlo a un cliente

Todo está en `index.html`:

- **WhatsApp:** cambiá `var WHATSAPP = '50370000000';` por el número del negocio, con código de país y sin `+` ni espacios.
- **Precios y datos:** reemplazá los textos entre corchetes, como `[TU PRECIO]` o `[PRIMA]`.
- **Fotos:** están en `img/`, numeradas en el orden del recorrido (`01-se-acerca.jpg` … `09-se-va.jpg`). Para otro carro, reemplazá cada foto por la toma equivalente con el mismo nombre: verticales, 1080 px de ancho y comprimidas a unos 200 KB. El movimiento de cámara de cada toma está en el atributo `data-cam` de su escena: `[escala, foco_x, foco_y]` al inicio (`a`) y al final (`b`) de la toma.
- **Venta o alquiler:** los textos de cada modo están en los atributos `data-venta` y `data-alquiler`.

Es un solo archivo HTML más la carpeta de fotos, sin dependencias: se abre con doble clic o se publica en cualquier hosting estático.
