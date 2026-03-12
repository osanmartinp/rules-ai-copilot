# Copilot Global Instructions

Estas reglas aplican a **todas** las sesiones de este workspace. El agente debe leerlas y respetarlas siempre, sin excepción.

---

## Reglas generales

- Leer y aplicar todos los archivos en `instructions/` antes de generar cualquier código.
- Nunca modificar los archivos listados en `instructions/protected-files.instructions.md` sin confirmación explícita del usuario.
- Seguir las convenciones de nomenclatura definidas en `instructions/naming.instructions.md`.
- Respetar la arquitectura descrita en `instructions/architecture.instructions.md`.
- Ante la duda, preguntar antes de actuar.

## Lo que el agente NO debe hacer

- Reescribir código funcional que no fue pedido.
- Agregar dependencias nuevas sin mencionarlo primero.
- Cambiar configuraciones de entorno, CI/CD o infraestructura.
- Generar código con `any` en TypeScript, queries sin sanitizar, o secrets hardcodeados.
- Borrar o sobreescribir archivos sin confirmación.

## Idioma

- El código y los comentarios técnicos deben estar en **inglés**.
- Las respuestas al usuario pueden estar en **español** si el usuario escribe en español.
