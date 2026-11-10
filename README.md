# Proyecto CSS - Tienda Gamer

## Información del aprendiz

- **Aprendiz:** Jesús Arturo Rincón Villamizar
- **Programa:** Análisis y Desarrollo de Software (ADSO)
- **Institución:** SENA
- **Proyecto:** Tienda Gamer

## Descripción del proyecto

Este proyecto consiste en desarrollar una página web para una tienda de tecnología y productos gamer, utilizando HTML5 y CSS3.

Durante las actividades se trabajaron los selectores CSS, la aplicación de colores, la herencia, la cascada, la especificidad, el modelo de caja y los fondos de los diferentes elementos.

---

# Actividad 1: Selectores, herencia y cascada en CSS

## Objetivo

Aprender a aplicar estilos a los elementos HTML utilizando selectores CSS y comprender cómo funcionan la herencia, la cascada y la especificidad.

## Trabajo realizado

Se aplicaron diferentes colores a los elementos de la página:

- Menú principal: azul.
- Menú secundario: verde.
- Pie de página: morado.
- Botones: rojo y naranja.
- Botón destacado: rosa.

## Selectores utilizados

Se trabajaron los siguientes selectores:

- **Selector de elemento:** permite aplicar estilos a elementos como `body`, `header` y `footer`.
- **Selector descendiente:** permite seleccionar elementos que se encuentran dentro de otros elementos.
- **Selector de clase:** permite aplicar estilos mediante clases como `.btn` y `.comprar`.
- **Selector combinado:** permite seleccionar elementos que tienen varias clases.

## Herencia

Se utilizó la herencia para comprender cómo algunas propiedades, como el color y la fuente, pueden transmitirse desde un elemento padre hacia sus elementos hijos.

## Cascada y especificidad

Se realizaron pruebas con diferentes reglas CSS para observar cómo se determina qué estilo tiene prioridad.

Se utilizaron las clases:

```css
.btn {
    color: #dc3545;
}

.comprar {
    color: #fd7e14;
}

.btn.comprar.destacado {
    color: #d63384;
}
```

Se comprobó que la especificidad de un selector puede hacer que una regla tenga prioridad sobre otra.

---

# Actividad 2: Modelo de caja y fondos

## Objetivo

Comprender cómo se organizan los elementos HTML mediante el modelo de caja y cómo aplicar colores e imágenes de fondo utilizando CSS.

## Trabajo realizado

Se realizaron los siguientes cambios:

1. Se agregó el modelo de caja universal.
2. Se asignaron diferentes colores de fondo a las secciones.
3. Se agregó una imagen de fondo al encabezado.
4. Se aplicaron propiedades de margen y relleno a los productos.
5. Se organizaron los cuatro productos horizontalmente, cada uno dentro de su propio cuadro.

## Modelo de caja

Se utilizó la siguiente regla:

```css
* {
    box-sizing: border-box;
}
```

Esta propiedad permite controlar mejor las dimensiones de los elementos, incluyendo el contenido, el relleno y los bordes.

## Fondos

Se utilizaron las siguientes propiedades:

- `background-color`: establece el color de fondo.
- `background-image`: permite colocar una imagen de fondo.
- `background-size`: controla el tamaño de la imagen.
- `background-position`: establece la posición de la imagen.
- `background-repeat`: controla si la imagen se repite.

## Margin y Padding

- **Margin:** es el espacio externo que separa un elemento de otros elementos.
- **Padding:** es el espacio interno entre el contenido y el borde del elemento.

## Organización de los productos

Se agregaron cuatro productos a la tienda:

| Producto | Precio |
|---|---:|
| Portátil Pro 14 | $3.200.000 |
| Teclado Mecánico | $280.000 |
| Audífonos Studio | $450.000 |
| Disco SSD 1 TB | $320.000 |

Cada producto tiene su propio cuadro con nombre, descripción, precio y botón de compra.

Para organizarlos horizontalmente se utilizó:

```css
.producto {
    display: inline-block;
    vertical-align: top;
    width: 23%;
    padding: 20px;
    margin: 0 1% 15px 0;
    border: 1px solid #cccccc;
}
```

No se utilizaron Flexbox ni CSS Grid para esta distribución.

## Hallazgos: El modelo de caja

### ¿Qué sucede cuando se utiliza un margin muy grande?

Los elementos quedan más separados y pueden ocupar más espacio dentro de la página, modificando su distribución.

### ¿Por qué es importante utilizar box-sizing: border-box?

Porque facilita el control del tamaño de los elementos y evita que el padding y los bordes aumenten las dimensiones establecidas.

---

# Actividad 3: Identidad visual (Custom Properties y Tipografías)

## Objetivo

Centralizar colores, tipografía y espaciados en variables CSS dentro de `:root`, para que toda la interfaz responda a un único estándar visual.

## Trabajo realizado

1. Se creó la rama `feature/identidad-visual`.
2. Se declaró `:root` al inicio de `style.css` con variables de color, tipografía y espaciado.
3. Se vinculó la fuente **Poppins** desde Google Fonts en el `<head>` y se asignó a `--fuente-principal`.
4. Se reemplazaron todos los colores y medidas de `margin` y `padding` por `var()`.

## Hallazgos: Centralización de Identidad Visual y Espaciado

### 1. Variables declaradas

| Tipo | Variable | Valor |
|---|---|---|
| Color | `--color-primario` | #0b5ed7 |
| Color | `--color-secundario` | #198754 |
| Color | `--color-acento` | #6f42c1 |
| Color | `--color-boton` | #dc3545 |
| Color | `--color-boton-comprar` | #fd7e14 |
| Color | `--color-fondo` | #f2f2f2 |
| Color | `--color-oscuro` | #343a40 |
| Color | `--color-superficie` | #ffffff |
| Color | `--color-tarjeta` | #e9ecef |
| Color | `--color-aside` | #d1e7dd |
| Color | `--color-borde` | #cccccc |
| Color | `--color-texto` | #333333 |
| Color | `--color-texto-fuerte` | #212529 |
| Color | `--color-texto-claro` | #ffffff |
| Tipografía | `--fuente-principal` | "Poppins", sans-serif |
| Espaciado | `--espaciado-pequeno` | 10px |
| Espaciado | `--espaciado-medio` | 15px |
| Espaciado | `--espaciado-grande` | 20px |
| Espaciado | `--espaciado-xl` | 30px |

### 2. Ventaja de reutilizar medidas de margen y relleno

Antes, valores como 15px y 20px estaban escritos en muchos selectores. Ahora cada espacio sale de una escala de cuatro medidas, así que las tarjetas, el contenido y el menú tienen la misma proporción de aire. Si el cliente pide más separación, se cambia una sola línea en `:root` y no se corre el riesgo de dejar espacios desiguales.

### 3. Cómo `:root` previene colisiones visuales

Con un único punto de verdad, dos reglas no pueden terminar con tonos casi iguales ni con medidas distintas por error (por ejemplo 14px frente a 15px). A medida que la hoja crece, cada regla nueva consulta los mismos tokens, y la paleta y los espacios se mantienen coherentes.

---

# Actividad 4: Pseudoclases y pseudoelementos

## Objetivo

Dar vida a la interfaz respondiendo a las acciones del usuario (pseudoclases) e inyectando detalles decorativos desde CSS (pseudoelementos), sin ensuciar el HTML.

## Trabajo realizado

1. Se creó la rama `feature/interactividad-css`.
2. En el menú lateral (`aside`): `:hover` cambia fondo y texto, `::before` inyecta un indicador `• ` y `:focus` muestra un contorno con `--color-secundario`.
3. En los botones de compra: `:hover` cambia el fondo, `:active` simula el hundimiento y `:focus-visible` muestra un contorno para el teclado.
4. En los productos: `h2::after` dibuja una línea decorativa y `.producto::after` inyecta las insignias "¡Oferta!" (primer producto) y "Nuevo" (último).
5. Los colores nuevos se agregaron al `:root` (`--color-boton-comprar-hover`, `--color-oferta`, `--color-nuevo`, `--transicion`).

## Hallazgos: Pseudoclases y Pseudoelementos

### 1. Diferencia entre pseudoclase y pseudoelemento

Una pseudoclase (`:hover`, `:active`, `:focus`) selecciona un elemento que ya existe cuando está en cierto estado, es decir, reacciona a un evento del usuario. Un pseudoelemento (`::before`, `::after`) crea una parte virtual nueva, que no está en el HTML, y le inyecta contenido o decoración.

### 2. Importancia de `:focus` para la accesibilidad

Quien navega con la tecla Tab (por teclado o lector de pantalla) no usa el cursor, por lo que `:hover` no le sirve. `:focus` le muestra un contorno visible que indica en qué enlace está. Sin eso, no sabría dónde se encuentra y la página sería casi inutilizable.

### 3. Por qué decorar con `::before` / `::after`

Los adornos como insignias o iconos no son contenido, son presentación. Hacerlos con CSS mantiene el HTML limpio y semántico, evita etiquetas vacías, y permite cambiarlos en un solo lugar sin tocar el documento.

---

# Actividad 5: Arquitectura modular y metodología BEM

## Objetivo

Reorganizar el proyecto sin cambiar su aspecto: dividir el CSS en módulos independientes y nombrar las clases con la metodología BEM (Bloque, Elemento, Modificador).

## Trabajo realizado

1. Se creó la rama `feature/arquitectura-bem`.
2. **Modularización:** se creó la carpeta `components/` con un archivo por componente y se conectaron con `@import` en `style.css`.
3. **Marcado BEM:** se reescribieron las clases de `index.html`, eliminando las genéricas (`.producto`, `.precio`, `.contenedor`, `.comprar`).
4. **Modificadores:** `card--oferta`, `card--nuevo`, `btn--comprar`, y dos listos para usar: `card--destacada` y `btn--secundario`.
5. **Selectores planos:** se eliminaron los selectores anidados (`.producto h2`, `aside ul li a`, `header nav ul li a`) y cada regla depende de una sola clase.
6. Los módulos siguen usando las variables del `:root` con `var(--...)`.

## Estructura del proyecto

```
index.html
style.css                  (@import + :root + base)
README.md
components/
    encabezado.css         (bloques header y menu-principal)
    catalogo.css           (bloque catalog)
    tarjeta.css            (bloque card)
    botones.css            (bloque btn)
    menu-lateral.css       (bloque menu-lateral)
    pie.css                (bloque footer)
```

## Cambio de nombres de las clases

| Antes | Ahora (BEM) |
|---|---|
| `.producto` | `.card` |
| `.producto h2` | `.card__title` |
| `p` de descripción | `.card__description` |
| `.precio` | `.card__price` |
| `.btn.comprar` | `.btn.btn--comprar` |
| `.contenedor` | `.catalog__list` |
| `aside ul li a` | `.menu-lateral__link` |
| `header nav ul li a` | `.menu-principal__link` |
| `:first-child` (¡Oferta!) | `.card--oferta` |
| `:last-child` (Nuevo) | `.card--nuevo` |

## Hallazgos: Arquitectura BEM y Modularidad

### 1. Qué significa BEM y cómo se escribe

BEM significa **Bloque, Elemento, Modificador**. Un bloque es un componente independiente (`card`). Un elemento es una parte de ese bloque, unido con doble guion bajo (`card__title`). Un modificador es una variación, unido con doble guion medio (`card--oferta`). Visualmente: `bloque__elemento--modificador`.

### 2. Por qué dividir el CSS facilita el trabajo colaborativo

Cada persona puede trabajar en un archivo distinto (por ejemplo, una en `tarjeta.css` y otra en `botones.css`) sin pisar el trabajo de las demás, y los conflictos de Git son menos probables. Además, es más fácil encontrar dónde cambiar algo.

### 3. Cómo BEM evita la guerra de especificidad

Con selectores como `.producto h2` o `aside ul li a`, un selector más fuerte puede pisar a otro y obliga a usar reglas aún más pesadas. Con BEM, cada regla usa una sola clase (peso 10), así que todas tienen el mismo peso y gana la que se escribe después. Las reglas dejan de pisarse por accidente.

---

# Tecnologías utilizadas

- HTML5
- CSS3
- Git
- GitHub

# Conclusión

Durante estas cinco actividades se aprendieron conceptos fundamentales de CSS para mejorar la presentación de una página web.

En la primera actividad se trabajaron los selectores, la herencia, la cascada y la especificidad. En la segunda se aplicaron los conocimientos del modelo de caja, los fondos, los márgenes y los rellenos.

En la tercera se centralizaron los colores, la tipografía y los espaciados en variables CSS. En la cuarta se agregó interactividad con pseudoclases y decoración con pseudoelementos. En la quinta se modularizó el CSS y se aplicó la metodología BEM. Finalmente, se organizaron cuatro productos en una misma fila horizontal, cada uno con su propio cuadro y su información correspondiente.