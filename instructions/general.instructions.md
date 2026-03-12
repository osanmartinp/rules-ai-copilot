---
applyTo: "**"
---

# Buenas prácticas generales de código

## Principios base

- Seguir los principios **SOLID**, **DRY** y **KISS**.
- Preferir código legible sobre código "inteligente".
- Cada función debe tener una sola responsabilidad.
- Limitar la longitud de las funciones a un máximo de **40 líneas**.
- Limitar la profundidad de anidamiento a **3 niveles** como máximo.

## Funciones flecha y retorno implícito

- Usar **funciones flecha** (`arrow functions`) en lugar de funciones tradicionales dentro de métodos de clases.
  - **Excepción**: los métodos de primer nivel en controladores, servicios, DAOs y clases similares pueden definirse como métodos de clase normales.
  - Correcto: `const suma = (a: number, b: number): number => a + b;`
  - Incorrecto: `function suma(a: number, b: number): number { return a + b; }`
- Usar **retorno implícito** en funciones flecha cuando el cuerpo es una sola expresión:
  - Correcto: `const doble = (n: number): number => n * 2;`
  - Incorrecto: `const doble = (n: number): number => { return n * 2; }`

## Manejo de errores

- Nunca silenciar errores con bloques `catch` vacíos.
- Registrar siempre los errores con contexto suficiente (mensaje, stack, datos relevantes).
- No usar `console.log` en producción; usar un logger estructurado.
- Propagar errores al nivel correcto; no manejarlos todos en el mismo lugar.

## Comentarios

- No comentar el "qué" hace el código; comentar el "por qué" cuando no es obvio.
- Eliminar código comentado antes de hacer commit.
- Los TODOs deben llevar el nombre de quien lo pone y una fecha: `// TODO(nombre): descripción — 2026-03-12`.

## Tests

- Todo código nuevo debe tener tests unitarios.
- Los tests deben ser independientes entre sí (no compartir estado).
- Nombrar los tests con el patrón: `should [comportamiento esperado] when [condición]`.
- No mockear lo que no es necesario.

## Seguridad

- Nunca hardcodear secrets, tokens o contraseñas.
- Validar y sanitizar todos los inputs que vengan del exterior (usuario, API, base de datos).
- No usar versiones con vulnerabilidades conocidas en dependencias.
