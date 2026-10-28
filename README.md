# Catálogo de Productos - Jerarquía de Estilos CSS

Este proyecto corresponde a la **Subactividad 1** del programa de Análisis y Desarrollo de Software (SENA).

## Cálculo de Puntos de Especificidad

En CSS, el navegador decide qué estilo aplicar a un elemento basándose en el peso de sus selectores:

1. **Selector de Etiqueta / Pseudoelemento**: `1 punto` (Ejemplo: `a`, `p`, `h2`)
2. **Selector de Clase / Atributo / Pseudoclase**: `10 puntos` (Ejemplo: `.btn`, `.btn-comprar`, `:hover`)
3. **Selector de ID**: `100 puntos` (Ejemplo: `#btn-destacado`)

### Ejemplo práctico:

- `.btn-comprar` tiene un peso de **10 pts**.
- `#btn-destacado` tiene un peso de **100 pts**.

Aunque la clase se declare más abajo en el archivo CSS, la regla por ID prevalecerá debido a que posee mayor peso de especificidad. Para mantener un código limpio y fácil de mantener, la buena práctica consiste en refactorizar y trabajar con arquitectura basada en clases simples y compuestas.
