---

## Hallazgos: Pseudoclases y Pseudoelementos

1. **Diferencia funcional entre una pseudoclase y un pseudoelemento:**
   - Una **pseudoclase** (como `:hover`, `:active` o `:focus`) reacciona dinámicamente y se aplica a un elemento basándose en su estado actual o en la interacción del usuario[cite: 2]. Un **pseudoelemento** (como `::before` o `::after`) permite insertar o maquetar contenido visual directamente en el DOM virtual a través de CSS sin necesidad de alterar la estructura semántica del archivo HTML[cite: 1, 2].

2. **Importancia técnica de la pseudoclase `:focus` en accesibilidad web:**
   - Garantiza que los usuarios que navegan mediante tecnologías de asistencia o exclusivamente con el teclado (usando la tecla `Tab`) puedan identificar visualmente y con total claridad en qué sección o enlace se encuentran ubicados[cite: 2].

3. **Por qué es una buena práctica inyectar elementos decorativos desde CSS:**
   - Evita saturar el código HTML con etiquetas vacías o elementos puramente estéticos (como insignias de ofertas o iconos) que no aportan significado semántico al documento, manteniendo el código limpio, fácil de mantener y separando estrictamente la presentación visual de la estructura[cite: 1, 2].