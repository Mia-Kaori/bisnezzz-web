# Bisnezzz · Merch fanmade de música

## 1. Descripción del proyecto

**Bisnezzz** es una tienda online de ropa *streetwear* fanmade para personas a las que les apasiona la música, del K-pop al R&B. Ofrece diseños originales y ediciones limitadas, más elaborados que el merch oficial básico y diseñados en España. Las ventas se organizan en *drops* y preventas; el *drop* actual es **THE PANTS #001**.

La web permite **descubrir el catálogo, consultar una prenda en detalle y preparar una compra** en el carrito. También incluye un formulario para **solicitar un cambio de talla**, que responde a la principal preocupación de nuestras clientas: elegir bien la talla.

Proyecto realizado para la práctica **AC2.1 — Diseña y construye tu web** con HTML y CSS. Es un prototipo académico: no se realizan compras ni envíos reales y todos los datos de ejemplo son ficticios.

## 2. Web publicada

 **https://mia-kaori.github.io/bisnezzz-web/**

## 3. Páginas y recorrido recomendado

| Página | Archivo | Contenido |
|---|---|---|
| Inicio | `index.html` | Qué ofrece Bisnezzz y a quién va dirigida, *drop* actual, acceso al catálogo, prendas destacadas y ventajas. |
| Catálogo | `catalogo.html` | Buscador, filtros, resumen de resultados, 9 fichas en Grid (THE PANTS #001 destacada), foto ampliada de cada prenda y paginación. |
| Detalle | `detalle.html` | THE PANTS #001: fotos, precio, descripción, características, selector de talla, guía de medidas e información de envíos y devoluciones. |
| Carrito | `carrito.html` | Selección de ejemplo con 2 prendas, cantidades, precio unitario, subtotales, total, seguir comprando y tramitar pedido. |
| Formulario | `formulario.html` | Solicitud de cambio de talla con 9 campos agrupados y validación nativa. |
| Iniciar sesión | `login.html` | Acceso de demostración con correo y contraseña. |

**Recorrido recomendado (preparar una compra):**

1. **Inicio** → pulsa «Ver catálogo».
2. **Catálogo** → pulsa «Ver detalle de THE PANTS #001» (la única prenda con página de detalle).
3. **Detalle** → elige la talla, consulta la guía de medidas y pulsa «Añadir al carrito».
4. **Carrito** (menú superior) → revisa la selección de ejemplo y pulsa «Tramitar pedido».

**Otros recorridos:**

- **Cambio de talla:** enlace «Cambio de talla» del pie (en todas las páginas) o «¿No te queda bien? Solicita un cambio de talla» en el apartado *Devoluciones y reembolsos* del detalle.
- **Cuenta:** «Iniciar sesión» en el menú superior.

## 4. Abrir el proyecto en local

1. Clona el repositorio:
   ```
   git clone https://github.com/Mia-Kaori/bisnezzz-web.git
   ```
2. Entra en la carpeta `bisnezzz-web`.
3. Abre `index.html` en el navegador. También puedes abrir la carpeta en Visual Studio Code y usar la extensión **Live Server** (clic derecho en `index.html` → *Open with Live Server*).

No hace falta instalar nada: la web solo utiliza HTML y CSS. Las fuentes se cargan desde Google Fonts, así que sin conexión a internet se muestran las fuentes alternativas.

## 5. Funciones representadas pero no implementadas

Esta entrega es un prototipo estático. Cada limitación se indica en la propia página con un aviso visible.

| Función | Página | Qué ocurre en esta versión |
|---|---|---|
| Inicio de sesión | Login | No se crean cuentas ni se comprueban credenciales. |
| Búsqueda, filtros y paginación | Catálogo | Los controles se pueden usar, pero no modifican los resultados. El resumen «Mostrando 1–9 de 18 resultados» es un texto de ejemplo. |
| Recuperar el catálogo de un servicio | Catálogo | Las fichas están escritas directamente en el HTML. |
| Añadir al carrito | Detalle | El botón no añade la prenda. Se puede ver un carrito de ejemplo desde el menú. |
| Modificar cantidades, eliminar y recalcular | Carrito | Los botones no cambian la selección y los importes están escritos en el HTML. |
| Tramitar pedido y pagar | Carrito | No se realiza ningún pedido ni pago. |
| Enviar y guardar la solicitud | Formulario | La validación nativa sí funciona, pero los datos no se envían ni se guardan. |
| Páginas de detalle del resto de prendas | Catálogo | Solo THE PANTS #001 tiene página de detalle. |

Las acciones simuladas usan `<button type="button">`, para que no envíen ni recarguen la página. La adaptación completa a móvil se hará en la segunda práctica.

## 6. Uso de Flexbox y Grid

Todos los estilos están en `css/estilos.css`.

### Flexbox

| Componente | Selector | Uso |
|---|---|---|
| Cabecera | `header` | Logo y menú en los extremos (`justify-content: space-between`), con `flex-wrap` para la barra superior del *drop*. |
| Menú principal | `header nav ul` | Enlaces en fila con `gap`. |
| Pie de página | `footer` | Columnas con `flex: 2 1 20rem` y `flex: 1 1 10rem`, y `flex-wrap`. |
| Botones de la portada | `.acciones` | Acción principal y secundaria en fila, con `flex-wrap`. |
| Rail de destacados | `.rail` | Prendas en fila con `flex: 1 0 13rem`. |
| Buscador | `.buscador` | Etiqueta en una línea y campo con `flex: 1 1 20rem` junto al botón. |
| Ficha del catálogo | `.ficha` | Contenido en columna (`flex-direction: column`). |
| Paginación | `.paginacion ul` | Controles centrados con `gap`. |
| Selector de talla | `.selector-talla`, `.ticket` | Tickets de talla en fila con `flex-wrap`. |
| Cantidad del carrito | `.carrito-cantidad` | Etiqueta, botones − y + y campo, con `flex-wrap`. |
| Casillas y radios | `.condicion` y etiquetas de los grupos | Control y texto alineados. |

### Grid

| Componente | Selector | Uso |
|---|---|---|
| **Catálogo** | `.catalogo-grid` | 3 columnas flexibles (`repeat(3, minmax(0, 1fr))`), separación con `gap` y filas que crecen con su contenido. La primera ficha (THE PANTS #001) ocupa **2 columnas y 2 filas** (`grid-column: span 2; grid-row: span 2`) para destacar el *drop* actual. |
| Ficha destacada | `.ficha-destacada` | Cuadrícula interna: foto arriba, información a la izquierda y botón «Ver detalle» a la derecha. |
| Catálogo con filtros | `.catalogo-contenido` | Columna de filtros (`15rem`) y resultados (`1fr`). |
| Foto ampliada | `.ampliada-fotos` | Vista delantera y trasera, una al lado de otra. |
| Portada | `.presentacion` | Texto e imagen principal (`1.2fr 1fr`). |
| Ventajas | `.ventajas-lista` | Tres tarjetas en columnas iguales. |
| Detalle | `.detalle`, `.detalle-galeria` | Galería e información en dos columnas, y galería en columna. |
| Carrito | `.carrito`, `.carrito-fila` | Productos y resumen del pedido, y cada fila del carrito alineada en columnas. |

Se ha comprobado con DevTools a **1024 px y 1440 px** que no hay desplazamiento horizontal, recortes ni superposiciones.

## 7. Documentación de diseño y comprobación

Toda la documentación está en la carpeta [`docs/`](docs/):

- [Definición del proyecto: propósito, usuarios, contexto, tareas y recorrido](docs/definicion.md)
- [Bocetos iniciales de las seis páginas](docs/Bocetos%20Bisnezzz.pdf)
- [Revisión de los bocetos](docs/revision-bocetos.md)
- [Comprobaciones con DevTools](docs/devtools.md)
- [Comprobación de accesibilidad](docs/accesibilidad.md)
- [Prueba final de usabilidad y mejoras](docs/prueba-final.md)

## 8. Procedencia de imágenes y recursos

- **Logotipo e imágenes de producto** (`img/`): pertenecen a Bisnezzz y se usan con permiso del negocio. Las prendas son diseños propios de la marca.
- **Fotografía de la portada** (`img/marketing.png`): fotografía promocional de THE PANTS #001 de Bisnezzz. 
- **Fuentes:** [Anton](https://fonts.google.com/specimen/Anton) e [Inter](https://fonts.google.com/specimen/Inter), de Google Fonts, con licencia SIL Open Font License.
- **Optimización de imágenes:** [Squoosh](https://squoosh.app/), para reducir el peso de las fotos.
- **Textos, precios y datos:** propios de Bisnezzz. Los datos de pedidos, carrito y formularios son ficticios.

## 9. Herramientas de IA utilizadas

He utilizado **Claude** (Anthropic) como asistente durante el proyecto para:

- Según el enunciado organizar los requisitos por fases.
- Proponer y generar partes del código HTML y CSS a partir de mis decisiones de diseño y de mis bocetos.
- Comprobar contrastes y anchuras de pantalla.

Las decisiones de diseño y de contenido son mías. He revisado todo el código entregado y puedo explicarlo y modificarlo.
