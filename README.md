# Demo: recorrido de carro — Pickup 4x4 2023

Micrositio de demostración para concesionarios y rentadoras de carros en El Salvador: el carro se presenta como un recorrido en una sola página, de afuera hacia adentro, con modo **venta** y modo **alquiler**, precios y botón de WhatsApp.

**Ver en vivo:** https://josueaparicio.github.io/demo-recorrido-pickup/

## Para adaptarlo a un cliente

Todo está en `index.html`:

- **WhatsApp:** cambiá `var WHATSAPP = '50370000000';` por el número del negocio, con código de país y sin `+` ni espacios.
- **Precios y datos:** reemplazá los textos entre corchetes, como `[TU PRECIO]` o `[PRIMA]`.
- **Venta o alquiler:** los textos de cada modo están en los atributos `data-venta` y `data-alquiler`.

Es un solo archivo HTML, sin dependencias: se abre con doble clic o se publica en cualquier hosting estático.
