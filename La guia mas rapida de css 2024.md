# LA GUIA MÁS RÁPIDA DE CSS 2024

Bienvenidos a esta guía compacta de CSS, creada como una herramienta de ayuda rápida para la comunidad de desarrolladores web.

Presupongo que:

- Ya sabes agregar un archivo css a tu pagina

Por supuesto, puedo agregar una sección sobre cómo agregar estilos a una página al índice y reorganizar los elementos existentes. Aquí está el índice actualizado:

## Índice

1. [Conceptos Básicos de CSS](#1-conceptos-básicos-de-css)
2. [Estructura de un Archivo CSS](#2-estructura-de-un-archivo-css)
3. [Agregar Estilos a una Página](#3-agregar-estilos-a-una-página)
4. [Mobile First y Responsive Design](#4-mobile-first-y-responsive-design)
5. [Metodología BEM (Block Element Modifier)](#5-metodología-bem-block-element-modifier)
6. [Buenas Prácticas](#6-buenas-prácticas)
7. [Resetear CSS](#7-resetear-css)
   1. [Box-Sizing: Border-Box](#71-box-sizing-border-box)
8. [Flexbox](#8-flexbox)
9. [Grid](#9-grid)
10. [Herramientas Útiles para Avanzar](#10-herramientas-útiles-para-avanzar)
11. [Recursos de Aprendizaje](#11-recursos-de-aprendizaje)

## 1. Conceptos Básicos de CSS

- **CSS (Cascading Style Sheets)**: Usado para estilizar y dar formato a las páginas web.
- **Selectores**: Permiten seleccionar los elementos HTML a los que se les aplicará el estilo.
- **Propiedades y Valores**: Establecen cómo se deben mostrar los elementos seleccionados.

## 2. Estructura de un Archivo CSS

```css
selector {
  propiedad: valor;
}
```

Ejemplo:

```css
p {
  color: red;
  font-size: 16px;
}
```

## 3. Agregar Estilos a una Página

El CSS puede ser incorporado en una página web de varias maneras, cada una con sus propias ventajas y desventajas. Estos métodos incluyen estilos inline, internos y externos.

### Estilos Inline

Los estilos inline se aplican directamente en los elementos HTML utilizando el atributo `style`.

- **Ejemplo:**
  ```html
  <p style="color: red; font-size: 16px;">Texto con estilo inline.</p>
  ```

### Estilos Internos

Los estilos internos se colocan dentro de un elemento `<style>` en la sección `<head>` del documento HTML.

- **Ejemplo:**
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

### Estilos Externos

Los estilos externos se definen en archivos CSS separados.

- **Ejemplo:**
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

### Consideraciones

- **Mantenimiento**: Los estilos externos son más fáciles de mantener, especialmente en sitios web grandes.
- **Rendimiento**: Los estilos externos pueden ser almacenados en caché por el navegador, lo que mejora la velocidad de carga en visitas sucesivas.
- **Especificidad**: Los estilos inline tienen la mayor especificidad, lo que puede sobrescribir otros estilos definidos interna o externamente.

## 4. Mobile First y Responsive Design

- **Mobile First**: Diseña para dispositivos móviles primero y luego expande los estilos para pantallas más grandes.
- **Media Queries**: Utiliza consultas de medios para aplicar estilos condicionales según el tamaño de la pantalla.

  ```css
  @media (min-width: 600px) {
    .clase {
      propiedad: valor;
    }
  }
  ```

## 5. Metodología BEM (Block Element Modifier)

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

## 6. Buenas Prácticas

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

## 7. Resetear CSS

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

  ### 7.1 Box-Sizing: Border-Box

  - **`box-sizing: border-box`**:
    - Hace que el ancho y alto de un elemento incluyan el padding y el borde, no solo el contenido.
  - **Por qué se usa**:
    - Facilita el cálculo de tamaños de elementos, especialmente al diseñar layouts.
    - Mejora la previsibilidad del tamaño de los elementos al cambiar el padding o el borde.
  - **¿Por qué no es el predeterminado en navegadores?**:
    - El valor por defecto de `box-sizing` es `content-box` por razones históricas y de compatibilidad con la web antigua.
    - `content-box` excluye el padding y el borde del ancho y alto del elemento, lo cual era el comportamiento estándar antes de la introducción de `border-box`.

## 8. Flexbox

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

## 9. Grid

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

## 10. Herramientas Útiles para avanzar

- **Preprocesadores como SASS o LESS**: Permiten variables, mixins, anidación, etc.
- **Framework CSS como Bootstrap o Tailwind**: Proporcionan componentes preestilizados y sistemas de grid.

## 11. Recursos de Aprendizaje

- Documentación oficial (MDN Web Docs, W3Schools)
- Tutoriales en línea (Codecademy, freeCodeCamp, mi recomendacion: Youtube)
- Aprender Flexbox jugando: [FlexFroggy](https://flexboxfroggy.com/)
- Aprender GridCSS jugando: [Grid Garden](https://cssgridgarden.com/)
