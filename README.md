# CAPITULO 8 - Propiedades y Contenedores CSS (Container Queries)
Los CSS Container Queries son el mismo concepto de las Media Queries, pero en lugar de estar orientados a modificar los estilos dependiendo del tamaño de la página o dispositivo (viewport), lo hace dependiendo de un contenedor padre (o ancestro). De esta forma, podemos cambiar el tamaño de ciertos elementos y hacer que tengan una forma o unos estilos dependiendo del contexto donde se encuentren.

------------

### ELEMENTO CONTENEDOR
Para empezar tenemos que determinar cuál será el elemento contenedor al que vamos a hacer referencia. En dicho elemento, necesitaremos establecer las siguientes propiedades:

#### PROPIEDADES

**Propiedad container-name:** La propiedad container-name le da un nombre de contenedor al elemento en el que nos encontramos. Sin este nombre no podremos hacer referencia luego, en la regla @container.

**ejemplo:**

```css
.container {
  container-name: titulo;
}
```

**Propiedad container-type:** La propiedad container-type, establece el tipo de tamaño que va a tener el contenedor en cuestión, donde puede ser:
 - size: Elementos de tipo bloque (alto y ancho).
 -  inline-size: Elementos de tipo linea (solo ancho).
 
**ejemplo**
```css
 .container {
  container-name: titulo;
  container-type: inline-size;
}
```
**Propiedad container:** En esta propiedad podemos indicar **dos valores**, el valor de la propiedad **container-name** y el valor de la propiedad **container-type**, pero siempre separadas por un **/**.

**ejemplo**

```css
 .container {
  container: titulo / inline-size;
}
```
------------
### REGLA CONTAINER
Una vez tenemos nuestro contenedor definido, debemos establecer una regla @container que es muy parecido a las reglas @media, pero en este caso establece una condición para aplicar estilos a un contenedor en concreto.

**SINTAXIS**
```css
@container <nombre del contenedor> (<condición>)
```
**Ejemplo**
```css
.container {
  border: 1px solid red;
  color: black;
  container: titulo;
}

@container logo (width <= 550px) {
  .h1 {
    color: blue;
  }
}
```

------------

### UNIDADES DE CONTENEDORES
Cuando nos encontramos en el interior de una regla @container podemos utilizar ciertas unidades especiales como cqw, cqh, cqi, cqb, cqmin o cqmax.
Los componentes que usan unidades de longitud relativas a su contenedor son más flexibles para su uso en diferentes contenedores sin tener que recalcular valores de longitud concretos.

**Las unidades de longitud de la consulta del contenedor son:**
- cqw: 1% del ancho de un contenedor de consulta
- cqh: 1% de la altura de un contenedor de consulta
- cqi: 1% del tamaño en línea de un contenedor de consulta
- cqb: 1% del tamaño del bloque de un contenedor de consulta
- cqmin: El valor más pequeño de uno cqi o cqb
- cqmax: El valor mayor de uno cqi u otro cqb

```css
@container (width > 700px) {
  .card h2 {
    font-size: max(1.5em, 1.23em + 2cqi);
  }
}
```

# CAPITULO 9 - Filtros y Efectos Visuales avanzados

Los filtros en CSS permiten añadir efectos visuales, como sepia, ajustes de brillo, contraste u otros, directamente desde el navegador y de manera instantánea, sin modificar de forma permanente la imagen original.

Se pueden aplicar desde dos propiedades CSS diferentes:

Propiedad  | Descripción
------------- | -------------
Filter  | Aplica un filtro concreto a un elemento HTML y todos los de su interior.
backdrop-filter  | 	Aplica un filtro concreto al fondo de un elemento HTML, sin que afecte a su interior.

### PROPIEDAD FILTER
filter acepta funciones de filtrado (por ejemplo, blur(), brightness(), contrast(), grayscale(), sepia()) que modifican la representación visual del elemento en el renderizado final de la página.
```css
img {
  filter: grayscale(100%);
  transition: filter 1s;
  width: 200px;
}

img:hover {
  filter: grayscale(0%);
}
```
#### FUNCIONES DE FILTROS
Función  | Significado | Valor
------------- | ------------- | -------------
grayscale  | Escala de blanco y negro | percent - number
blur | 	Desenfoque Gausiano | size
sepia | Grado de color sepia | percent - number
saturate | Grado de saturación | percent - number
opacity | Grado de transparencia | percent - number
brightness | Brillo | percent - number
contrast | Contraste | percent - number
hue-rotate | Rotación de color (matiz) | angle
invert | Invertir | percent - number
drop-shadow | Sombra idéntica | posx posy size color

**PORCENTAJES O NÚMEROS**
- PERCENT: Valor porcentual (0%, 50%,100%,....)
- NUMBER: Valor númerico (0, 0.5, 1,.....)

**ejemplo grayscale**
```css
#img1 {
    filter: grayscale(100%);
}
```
**ejemplo blur**
```css
#img2 {
    filter: blur(5px);
}
```
**ejemplo sepia**
```css
#img3 {
    filter: sepia(100%);
}
```
**ejemplo saturate**
```css
#img4 {
    filter: saturate(200%);
}
```
**ejemplo opacity**
```css
#img5 {
    filter: opacity(50%);
}
```
**ejemplo brigthness **
```css
#img6 {
    filter: brightness(230%);
}
```
**ejemplo contrast**
```css
#img7 {
    filter: contrast(250%);
}
```
**ejemplo invert**
```css
#img8 {
    filter: invert(80%);
}
```
**ejemplo hue-rotate**
```css
#img9 {
    filter: hue-rotate(230deg);
}
```
**ejemplo drop-shadow**
```css
#img10 {
    filter: drop-shadow(5px 5px 10px black);
}
```

### PROPIEDAD BACKDROP-FILTER
La propiedad backdrop-filter en CSS sirve para aplicar efectos visuales (como desenfoque, brillo, contraste, etc.) al fondo que hay detrás de un elemento, sin alterar el contenido interno de ese mismo elemento.

Es decir, mientras que filter afecta directamente al elemento y a todo lo que contiene, backdrop-filter solo modifica la parte del fondo que se ve a través del elemento.

**ejemplo**
```css
#img11 {
    backdrop-filter: blur(10px);
}
```
##REFERENCIAS:
- Manz. (s. f.).  Filtros CSS En LenguajeCSS.com. 
https://lenguajecss.com/css/efectos/filtros-css/
##REFERENCIAS:
- Manz. (s. f.). CSS Container Queries En LenguajeCSS.com. 
https://lenguajecss.com/css/responsive-web-design/css-container-queries/
