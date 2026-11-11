# Revisión de los bocetos

Bocetos revisados: [Bocetos Bisnezzz.pdf](Bocetos%20Bisnezzz.pdf) (6 páginas: inicio, catálogo, detalle, carrito, formulario y login).

- **Revisado por:** Nataly, compañera de clase.
- **Fecha:** viernes 6 de noviembre de 2026.
- **Método:** se le entregaron los bocetos y se le pidió resolver las tres tareas sin indicarle dónde pulsar ni qué camino seguir.

## Registro

| Tarea | Qué entendió o intentó hacer | Dificultad detectada | Cambio propuesto |
|---|---|---|---|
| 1. Encontrar un elemento del catálogo y consultar sus características | Fue al catálogo desde el menú, localizó la ficha grande de THE PANTS #001 y llegó a su detalle con «Ver detalle». | Preguntó si la distribución del Grid, con la ficha grande, cambiaría al cambiar la colección. No quedaba claro si la ficha grande era fija o dependía del producto. | Aclarar qué prenda ocupa la ficha grande y cómo se mantiene al cambiar de colección. |
| 2. Localizar el carrito e identificar cómo continuar | Encontró «Carrito» en el menú superior e identificó «Tramitar pedido» como forma de continuar. | Ninguna. | Ninguno. |
| 3. Localizar el formulario y comprender qué información debe introducir | Encontró «Cambio de talla» en el pie y entendió los datos que pide el formulario. | Ninguna. | Ninguno. |

## Sugerencias incorporadas y descartadas

| Sugerencia | Decisión | Justificación |
|---|---|---|
| Aclarar si la ficha grande del catálogo cambia con la colección. | **Se mantiene el diseño y se define la regla.** | La ficha grande es intencionada: destaca siempre el ***drop* actual**, que es la prenda que más interesa vender. La distribución no depende de la prenda concreta: el primer elemento de la cuadrícula ocupa 2 columnas y 2 filas (`.catalogo-grid > li:first-child`). Cuando cambie la colección, basta con colocar el nuevo *drop* el primero en el HTML y darle la clase `ficha-destacada`. El resto de fichas se reorganizan solas en la cuadrícula. |

## Resultado

Las tres tareas se completaron con los bocetos. La única duda fue sobre el Grid del catálogo y se resolvió definiendo qué prenda ocupa la ficha destacada, sin cambiar el diseño. Después de la revisión, el profesor también revisó los bocetos y dio el visto bueno para pasar a la fase de desarrollo.
