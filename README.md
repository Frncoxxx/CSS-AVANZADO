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
