## Hallazgos: Arquitectura BEM y Modularidad

### 1. ¿Qué significa la sigla BEM y cómo se escribe visualmente?

**BEM** significa **Bloque, Elemento, Modificador** (_Block, Element, Modifier_). Es una convención de nomenclatura para clases CSS que organiza la interfaz en componentes independientes:

- **Bloque (`.bloque`):** Representa un componente independiente y reutilizable (ejemplo: `.card`, `.btn`, `.menu-lateral`).
- **Elemento (`.bloque__elemento`):** Es una parte interna que pertenece a un bloque y no tiene sentido por sí sola. Se escribe con **doble guion bajo `__`** (ejemplo: `.card__title`, `.card__price`).
- **Modificador (`.bloque--modificador`):** Define una variación de apariencia o estado de un bloque o elemento. Se escribe con **doble guion medio `--`** (ejemplo: `.card--destacada`, `.btn--destacado`).

### 2. ¿Por qué dividir el CSS en varios archivos facilita el trabajo colaborativo?

Separar la hoja de estilos maestra en pequeños módulos independientes (`cards.css`, `boton.css`, `menu-lateral.css`) permite que varios desarrolladores trabajen al mismo tiempo en distintos componentes sin pisarse el código ni generar conflictos al hacer _merge_ en Git. Además, hace que encontrar y corregir errores visuales sea mucho más rápido que buscar en un solo archivo gigante.

### 3. ¿Cómo evita esta metodología la guerra de especificidad (Cascada)?

Tradicionalmente, al anidar selectores (como `aside ul li a` o `.catalogo article h2`), el peso de especificidad sube y obliga a usar selectores cada vez más largos o `!important` para sobrescribir estilos. Con BEM, cada etiqueta recibe su propia clase plana y única (ejemplo: `.menu-lateral__link`), manteniendo todos los selectores en un **peso plano de 10 (una sola clase)**. Esto elimina colisiones accidentales y hace que los estilos sean totalmente predecibles.
