# Prueba final de usabilidad y mejoras

## Prueba con un compañero

- **Participante:** Nataly, compañera de clase (la misma persona que revisó los bocetos).
- **Fecha:** miércoles 11 de noviembre de 2026.
- **Versión probada:** web publicada en https://mia-kaori.github.io/bisnezzz-web/ (ordenador).
- **Método:** las mismas tres tareas de la revisión de los bocetos, empezando siempre desde el inicio y sin indicarle dónde pulsar ni qué camino seguir. Se le pidió que pensara en voz alta y se anotó lo que hacía y comentaba.

| Tarea | Resultado | Qué hizo y dificultades observadas | Cambio realizado después de la prueba |
|---|---|---|---|
| 1. Encontrar un elemento del catálogo y consultar sus características | **Autónoma** | Pulsó «Ver catálogo» en el inicio para ver lo que había disponible y llegó al detalle de THE PANTS #001. No dudó. Comentó que le gustaba la tabla de medidas. Quiso ver los detalles de otras prendas: como la foto cambiaba al pasar el ratón, la pulsó y se abrió la foto ampliada. | Ninguno. |
| 2. Localizar el carrito e identificar cómo continuar | **Autónoma** | Fue al carrito desde el menú superior e identificó el botón «Tramitar pedido» como forma de continuar con la compra. No dudó. | Ninguno. |
| 3. Localizar el formulario y comprender qué información debe introducir | **Autónoma** | Fue al apartado «Ayuda» del pie y pulsó «Cambio de talla». No dudó. | Ninguno. |

Al terminar, se le preguntó si cambiaría algo y respondió que no.

## Observaciones valoradas

| Observación | ¿Problema de uso o función no implementada? | Decisión y justificación |
|---|---|---|
| 1. Quería ver los detalles de otras prendas y pulsó su foto, porque el cambio de imagen al pasar el ratón le indicó que se podía pulsar. | **Función no implementada.** El enunciado solo exige una página de detalle, y la única que existe es la de THE PANTS #001, identificada con su botón «Ver detalle». | **Sin cambios en esta entrega.** La foto ampliada cubre en parte su necesidad, porque muestra la prenda por delante y por detrás. Que pulsara la foto confirma que el efecto de pasar el ratón comunica que es interactiva. En la siguiente práctica se valorará crear las páginas de detalle del resto de prendas. |
| 2. Le gustó la tabla de medidas del detalle. | Observación positiva; no es un problema. | **Se mantiene.** Confirma que la decisión responde a la principal preocupación de las usuarias definida en el análisis: las medidas de la prenda. |

## Mejoras realizadas respecto a los bocetos

| Página | En el boceto | En la web final | Justificación |
|---|---|---|---|
| Todas | Público: fans del K-pop | Fans de la música en general | El catálogo incluye otros artistas y diseños propios. |
| Todas | Menú «Carrito (2)» | «Carrito» | En este prototipo el carrito no se actualiza: un número fijo no reflejaría su estado real y podría confundir. El contador se añadirá cuando se implemente con JavaScript. |
| Catálogo | Filtro «Disponibilidad» | Filtro «Artista» | Las usuarias buscan por artista. |
| Catálogo | 4 columnas, prendas agotadas | 3 columnas, todas disponibles o en preventa | El catálogo cambió y todas las prendas actuales están disponibles o en preventa. Ver muchas prendas agotadas al entrar resulta frustrante para quien viene a comprar. Con 3 columnas, a 1024 px y con los filtros al lado, cada ficha mide unos 205 px (con 4 serían unos 150 px), así que la foto y el texto se leen mejor. |
| Catálogo | Foto ampliada solo prevista para la fase de JavaScript | Foto ampliada con CSS (`:target`), con vista delantera y trasera | Permite ver la prenda en grande sin JavaScript. |
| Catálogo | — | La página actual de la paginación lleva subrayado, además del fondo | Se distingue con algo más que el color y no se confunde con el `:hover`. |
| Detalle | Etiquetas «Edición limitada», «Baggy pants» y «Regalo» | Eliminadas | Repetían la información de las características. |
| Detalle | Delante y detrás con botones de opción | Las dos fotos visibles, una debajo de otra | Más sencillo y la vista trasera se ve también con el teclado. |
| Detalle | Medidas: cintura, cadera y largo | Cintura, largo, entrepierna y ancho en la rodilla, con la tabla abierta por defecto | Son las medidas reales de un pantalón *baggy*. Al estar abierta, el enlace «Guía de tallas» lleva directamente a la tabla en todos los navegadores. |
| Formulario | Obligatorios con asterisco (*) | Texto «(obligatorio)» y «(opcional)» | No hay que interpretar un símbolo. |
| Formulario | Primera versión: `max="2026-12-31"` en la fecha de recepción | `max="2027-12-31"` | Permite pedir el cambio a quien reciba la preventa en enero. |

## Mejoras surgidas de las comprobaciones

| Problema detectado | Corrección | Justificación |
|---|---|---|
| En la foto ampliada del catálogo, el Tab llevaba el foco detrás de la foto. | El resto de la página se oculta con `visibility: hidden` mientras la foto está abierta. | El foco siempre es visible y el recorrido con el teclado es lógico. |
| El subrayado de la página actual del menú tenía un contraste de 2,31:1. | Color #A8285F, con 6,14:1. | La página actual se reconoce mejor y el indicador se ve con claridad. |
| Al ampliar al 200 %, dos prendas de Destacados quedaban fuera de la vista y no se alcanzaban con el teclado. | `flex-wrap: wrap` en el rail dentro de la media query de ampliación. | No se pierde contenido al ampliar. |
| La barra del «perchero» creaba un desplazamiento horizontal en el rail a 1024 y 1440 px. | `padding-inline` en el contenedor `.armario`. | Sin desplazamientos horizontales no deseados. |
| En el detalle, la talla y la casilla decían «obligatoria» sin serlo. | Textos cambiados a «Elige tu talla» y sin «(obligatorio)». | Las instrucciones coinciden con el comportamiento real de los controles. |
