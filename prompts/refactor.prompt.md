---
agent: agent
description: Refactoriza el código seleccionado aplicando las reglas del proyecto
---

Revisa el código seleccionado o el archivo indicado y aplica las siguientes mejoras, respetando siempre las reglas definidas en `instructions/`:

1. **Nombres**: Verifica que variables, funciones y clases sigan las convenciones en `instructions/naming.instructions.md`.
2. **Responsabilidad única**: Si una función hace más de una cosa, divídela.
3. **Profundidad**: Reduce el anidamiento a un máximo de 3 niveles usando early returns o extracción de funciones.
4. **Errores silenciados**: Reemplaza cualquier `catch` vacío o con solo `console.log` por un manejo de error adecuado.
5. **Comentarios**: Elimina código comentado y comentarios que solo describen el "qué".
6. **Seguridad**: Marca con un comentario `// SECURITY: revisar` cualquier input externo que no esté siendo validado.

No cambies la lógica de negocio, solo la estructura y calidad del código.
Muestra un resumen de los cambios realizados al final.
