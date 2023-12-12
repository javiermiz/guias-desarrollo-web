# LA GUIA MÁS RÁPIDA DE CSS 2024

Bienvenidos a esta guía compacta de CSS, creada como una herramienta de ayuda rápida para la comunidad de desarrolladores web.

## Índice

### La Base

1. [Conceptos Básicos](#1-conceptos-básicos)
2. [Estructura de Archivos](#2-estructura-de-archivos)
   - [Selectores CSS](#21-selectores-css)
3. [Aplicación de Estilos](#3-aplicación-de-estilos)
4. [Responsive y Mobile First](#4-responsive-y-mobile-first)

### Lo Más Usado Actualmente

5. [Flexbox](#5-flexbox)
6. [Grid](#6-grid)

### Buenas Prácticas

7. [Metodología BEM](#7-metodología-bem)
8. [Normalizar CSS](#8-reset-css-y-box-model)
   - [Box-Sizing: Border-Box](#81-box-sizing-border-box)
9. [Buenas Prácticas](#9-buenas-prácticas)

### Herramientas y Recursos

10. [Herramientas Útiles](#10-herramientas-útiles)
11. [Recursos de Aprendizaje](#11-recursos-de-aprendizaje)

## LA BASE

### 1. Conceptos Básicos

- **CSS (Cascading Style Sheets)**: Usado para estilizar y dar formato a las páginas web.
- **Selectores**: Permiten seleccionar los elementos HTML a los que se les aplicará el estilo.
- **Propiedades y Valores**: Establecen cómo se deben mostrar los elementos seleccionados.

### 2. Estructura de un Archivo

#### Formato Básico

```css
selector {
  propiedad: valor;
}
```

#### 2.1 Selectores CSS

##### Selector de Clase

```html css
<style>
  .clase-ejemplo {
    color: blue;
  }
</style>

<div class="clase-ejemplo">Texto con color azul</div>
```

##### Selector de ID

```html
<style>
  #id-ejemplo {
    font-weight: bold;
  }
</style>

<div id="id-ejemplo">Texto en negrita</div>
```

##### Selector de Atributo

```html
<style>
  input[type='text'] {
    border-color: green;
  }
</style>

<input type="text" placeholder="Input con borde verde" />
```

##### Selector Hijo

```html
<style>
  div p {
    margin-left: 20px;
  }
</style>

<div>
  <p>Parrafo dentro de un div con margen izquierdo</p>
</div>
```

##### Selector de Hijo Directo

```html
<style>
  ul > li {
    list-style-type: none;
  }
</style>

<ul>
  <li>Elemento de lista sin estilo de lista</li>
</ul>
```

### 3. Aplicación de Estilos

El CSS puede ser incorporado en una página
web de varias maneras, cada una con sus propias ventajas y desventajas. Estos
métodos incluyen estilos inline, internos y externos.

#### Estilos Inline

Los estilos inline se aplican directamente en los elementos HTML utilizando el atributo `style`.

**Ejemplo:**

```html
<p style="color: red; font-size: 16px;">Texto con estilo inline.</p>
```

#### Estilos Internos

Los estilos internos se colocan dentro de un elemento `<style>` en la sección `<head>` del documento HTML.

**Ejemplo:**

```html
<head>
  <style>
    p {
      color: blue;
      font-size: 18px;
    }
  </style>
</head>
```

#### Estilos Externos

Los estilos externos se definen en archivos CSS separados.

**Ejemplo:**

- Archivo CSS (styles.css):
  ```css
  p {
    color: green;
    font-size: 20px;
  }
  ```
- HTML:
  ```html
  <head>
    <link rel="stylesheet" href="styles.css" />
  </head>
  ```

#### Consideraciones

- **Mantenimiento**: Los estilos externos son más fáciles de mantener, especialmente en sitios web grandes.
- **Rendimiento**: Los estilos externos pueden ser almacenados en caché por el navegador, lo que mejora la velocidad de carga en visitas sucesivas.
- **Especificidad**: Los estilos inline tienen la mayor especificidad, lo que puede sobrescribir otros estilos definidos interna o externamente.

### 4. Responsive y Mobile First

#### Media Queries

Las media queries son una herramienta fundamental en el diseño responsive. Permiten aplicar estilos CSS condicionales dependiendo del tamaño de la pantalla o de otras características del dispositivo. Por ejemplo, puedes tener un conjunto de estilos para pantallas pequeñas y otro para pantallas más grandes.

```css
/* Estilos para pantallas menores a 600px */
.clase {
  propiedad: valor;
}

/* Estilos para pantallas 600px o más */
@media (min-width: 600px) {
  .clase {
    propiedad: valor;
  }
}
```

#### Mobile First

"Mobile First" es un enfoque de diseño en el que comienzas desarrollando los estilos del sitio web para dispositivos móviles primero y luego expandes o adaptas los estilos para pantallas más grandes. Este enfoque es beneficioso porque:

- La mayoría de las personas usa dispositivos móviles para navegar en internet, por lo que priorizar esta experiencia es esencial.
- Los sitios web diseñados con el enfoque Mobile First suelen tener tiempos de carga más rápidos y son generalmente más accesibles.
- Facilita la adaptación a diferentes tamaños de pantalla, ya que es más sencillo escalar un diseño de móvil a desktop que al revés.

## Lo Más Usado Actualmente

### 5. Flexbox

- **Flexbox**: Un modelo de diseño unidimensional que ofrece un control eficiente del espacio interior y la alineación de los elementos en un contenedor.
- **Uso**:
  - Define un contenedor flex con `display: flex`.
  - Ajusta la disposición de los elementos hijos (horizontal o vertical) y su alineación.

**Ejemplo**:

```css
.contenedor {
  display: flex;
  justify-content: center; /* Alineación horizontal */
  align-items: center; /* Alineación vertical */
}
```

### 6. Grid

- **Grid**: Un sistema de diseño bidimensional que permite manejar filas y columnas.
- **Uso**:
  - Establece un contenedor de cuadrícula con `display: grid`.
  - Define filas y columnas y la colocación de los elementos.

**Ejemplo**:

```css
.grid-contenedor {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* 3 columnas de 1 fraccion cada una */
  grid-gap: 10px; /* Espacio entre celdas */
}
```

## Buenas Prácticas

### 7. Metodología BEM

Facilita el mantenimiento del código CSS y mejora la legibilidad.

- **Bloque**: Componente independiente.
- **Elemento**: Parte de un bloque que no tiene sentido por sí mismo.
- **Modificador**: Variante o extensión de un bloque o elemento.

Ejemplo:

```css
.bloque {
}

.bloque__elemento {
}

.bloque--modificador {
}
```

### 8. Normalizar CSS

- **Resetear CSS**: Elimina los estilos por defecto del navegador para tener un punto de partida consistente.
- **Por qué se usa**:
  - Los navegadores tienen estilos predeterminados diferentes, lo que puede llevar a inconsistencias.
  - Un reset ayuda a garantizar que tu diseño se vea igual en todos los navegadores.
- **Ejemplo de Reset CSS**:

  ```css
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  ```

  #### 8.1 Box-Sizing: Border-Box

  - **`box-sizing: border-box`**:
    - Hace que el ancho y alto de un elemento incluyan el padding y el borde, no solo el contenido.
  - **Por qué se usa**:
    - Facilita el cálculo de tamaños de elementos, especialmente al diseñar layouts.
    - Mejora la previsibilidad del tamaño de los elementos al cambiar el padding o el borde.
  - **¿Por qué no es el predeterminado en navegadores?**:
    - El valor por defecto de `box-sizing` es `content-box` por razones históricas y de compatibilidad con la web antigua.
    - `content-box` excluye el padding y el borde del ancho y alto del elemento, lo cual era el comportamiento estándar antes de la introducción de `border-box`.

### 9. Buenas Prácticas extras

- **Organización**: Mantén tu CSS bien organizado y dividido en secciones.
- **Nomenclatura Consistente**: Usa nombres claros y descriptivos.
- **Evita la Especificidad Excesiva**: No anides selectores innecesariamente.
- **Uso de Variables CSS**: Para colores, fuentes y medidas comunes.

  ```css
  :root {
    --color-principal: #ff4500;
  }
  ```

- **Flexbox y Grid**: Para diseños responsivos y flexibles.
- **Mantenimiento y Escalabilidad**: Escribe CSS pensando en el futuro, facilitando cambios y adiciones.

## Herramientas y Recursos

### 10. Herramientas Útiles

- **Preprocesadores como SASS o LESS**: Permiten variables, mixins, anidación, etc.
- **Framework CSS como Bootstrap o Tailwind**: Proporcionan componentes preestilizados y sistemas de grid.

### 11. Recursos de Aprendizaje

- Documentación oficial (MDN Web Docs, W3Schools)
- Tutoriales en línea (Codecademy, freeCodeCamp, mi recomendacion: Youtube)
- Aprender Flexbox jugando: [FlexFroggy](https://flexboxfroggy.com/)
- Aprender GridCSS jugando: [Grid Garden](https://cssgridgarden.com/)
