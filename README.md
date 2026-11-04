## Hallazgos: Centralización de Identidad Visual y Espaciado

### 1. Lista Completa de Variables Declaradas (Tokens de Diseño)

En la pseudoclase `:root` se centralizaron las siguientes Custom Properties para estandarizar el sistema visual de la aplicación:

- **Variables de Color (Paleta Corporativa):**
  - `--color-primario`: Utilizado para destacar elementos principales como botones de acción y enlaces destacados.
  - `--color-secundario`: Aplicado en elementos visuales complementarios y estados secundarios.
  - `--color-fondo`: Define el tono base o lienzo de la interfaz y el catálogo de productos.
  - `--color-texto`: Tono contrastante optimizado para asegurar la legibilidad de los contenidos tipográficos.
- **Variables de Tipografía:**
  - `--fuente-principal`: Almacena la familia tipográfica limpia y legible importada desde Google Fonts para toda la interfaz.
- **Variables de Espaciado (Box Model):**
  - `--espaciado-pequeno (8px)`: Destinado a micro-separaciones internas, como la distancia entre etiquetas o textos cortos.
  - `--espaciado-medio (16px)`: Configurado como el relleno (_padding_) estándar dentro de las tarjetas de productos.
  - `--espaciado-grande (24px)`: Utilizado para los márgenes exteriores (_margin_) que separan las distintas secciones o bloques del catálogo.

---

### 2. Ventajas de Reutilizar Medidas de Margen y Relleno

La reutilización de tokens de espaciado en lugar de definir valores manuales (como `15px` o `20px`) en cada selector aporta importantes beneficios al proyecto:

- **Consistencia Visual Garantizada:** Elimina la arbitrariedad en el diseño. Al usar una escala fija, todas las tarjetas, contenedores y secciones mantienen proporciones de "aire" armónicas y equilibradas en toda la pantalla.
- **Mantenibilidad Eficiente:** Si en el futuro el cliente solicita un diseño más compacto o más espaciado, solo se debe cambiar el valor numérico una única vez en la variable global, impactando instantáneamente a toda la aplicación sin tocar decenas de selectores.
- **Reducción de Deuda Técnica:** Evita la duplicación innecesaria de código en la hoja de estilos, haciendo que el archivo CSS sea mucho más limpio, legible y fácil de transferir a otros desarrolladores.

---

### 3. Prevención de Colisiones Visuales mediante la Centralización en `:root`

A medida que un proyecto de software escala, las hojas de estilo tienden a volverse masivas y difíciles de controlar. La centralización en `:root` actúa como una **"central de mando"** que previene desajustes y colisiones visuales de la siguiente forma:

- **Evita la Fragmentación del Diseño:** Al definir los colores y espaciados en el nodo raíz, ningún componente nuevo puede "inventar" reglas aisladas; todos se ven obligados a alinearse al estándar maestro preexistente.
- **Control de Cascada Absoluto:** Al estar al inicio de la hoja de estilos, las Custom Properties heredan sus valores de forma fluida y descendente hacia cualquier elemento del DOM, minimizando errores por especificidad de selectores.
- **Dinamicidad y Flexibilidad:** Facilita la escalabilidad del sistema de diseño (por ejemplo, si se deseara implementar un modo oscuro o _Dark Mode_, bastaría con redefinir las variables bajo una clase específica, sin alterar la estructura interna de los componentes).
