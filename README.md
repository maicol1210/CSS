## Hallazgos: El Modelo de Caja

### 1. Diferencia práctica entre Margin y Padding

- **Padding (Relleno interno):** Es el espacio que se genera **dentro** de la caja, entre el contenido real (texto, imágenes) y su borde. Se usa para dar "oxígeno" y evitar que los textos choquen contra las paredes del contenedor.
- **Margin (Margen externo):** Es el espacio vacío que se genera **fuera** de la caja, actuando como un "campo de fuerza". Se usa para separar un elemento de sus vecinos y evitar colisiones visuales en la pantalla.

### 2. Por qué es obligatorio usar `box-sizing: border-box`

Por defecto, el navegador calcula el tamaño total de un elemento sumando el ancho (`width`) + el `padding` + el `border`. Esto hace que los elementos crezcan hacia afuera y rompan el diseño.
Al usar `box-sizing: border-box`, le ordenamos al navegador que mantenga el tamaño fijo que le dimos y que **comprima el padding y el borde hacia adentro**, garantizando una estructura matemática exacta y predecible.

### 3. Cómo se ven afectados los elementos hermanos ante un margen grande

Cuando se le aplica un margen exterior grande a un elemento, este empuja físicamente a sus elementos hermanos (hacia los lados o hacia abajo). Si el espacio total de la pantalla no es suficiente para contenerlos tras el empuje, los elementos hermanos se verán obligados a desplazarse o saltar de línea, alterando la posición de toda la interfaz.
