---
applyTo: "**"
---

# Arquitectura y patrones

El agente debe respetar las decisiones de arquitectura definidas aquí y no proponer cambios estructurales sin discutirlos primero.

---

## Capas de la aplicación

La aplicación sigue una arquitectura en capas. Cada capa solo puede depender de la capa inmediatamente inferior:

```
┌─────────────────────────┐
│  Controllers / Routes   │  ← Recibe requests, devuelve responses
├─────────────────────────┤
│       Services          │  ← Lógica de negocio
├─────────────────────────┤
│      Repositories       │  ← Acceso a datos
├─────────────────────────┤
│     Database / ORM      │  ← Motor de persistencia
└─────────────────────────┘
```

### Reglas de capas

- Los **controllers** no deben contener lógica de negocio.
- Los **services** no deben importar directamente modelos de ORM; usar repositorios.
- Los **repositories** no deben conocer la lógica de negocio ni los DTOs de la API.
- Nunca saltarse capas (e.g., un controller que accede directamente a la base de datos).

## Patrones permitidos

- **Repository Pattern** para abstracción de datos.
- **DTO (Data Transfer Object)** para entrada y salida de la API.
- **Dependency Injection** para servicios y repositorios.
- **Factory** para construir objetos complejos.

## Patrones prohibidos

- **God Object**: clases o módulos que hacen demasiado.
- **Singletons globales mutables**: evitar estado global compartido.
- **Lógica en modelos de ORM** (Active Record con lógica de negocio).

## Módulos y separación de responsabilidades

- Organizar por **dominio/feature**, no por tipo de archivo:
  ```
  # Correcto           # Incorrecto
  src/users/           src/controllers/
    controller.ts        users.controller.ts
    service.ts           products.controller.ts
    repository.ts      src/services/
    dto.ts               users.service.ts
  ```
- Cada módulo es independiente y se comunica con otros a través de interfaces, no importaciones directas de implementaciones.

## Manejo de estado (frontend)

- El estado local del componente se maneja con el mecanismo nativo del framework.
- El estado global solo para datos compartidos entre múltiples vistas.
- No duplicar en el estado global lo que puede derivarse de otros datos.
