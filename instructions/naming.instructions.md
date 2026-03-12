---
applyTo: "**"
---

# Convenciones de nomenclatura

Aplicar en todo el código generado o modificado.

---

## General

| Elemento           | Convención                         | Ejemplo                                     |
|--------------------|-------------------------------------|---------------------------------------------|
| Variables          | `camelCase`                        | `user`, `userId`                            |
| Constantes         | `UPPER_SNAKE_CASE`                 | `MAX_RETRY_ATTEMPTS`, `API_BASE_URL`        |
| Métodos            | `camelCase`                        | `getUserById`, `isActive`                   |
| Clases             | `PascalCase`                       | `UserService`, `PaymentGateway`             |
| Interfaces         | `PascalCase` precedido por `I`     | `IUserRepository`, `IOrderService`          |
| Types              | `PascalCase`                       | `UserDto`, `ApiResponse`                    |
| Enums (archivo)    | `kebab-case`                       | `order-status.enum.ts`                      |
| Enums (valores)    | `UPPER_SNAKE_CASE`                 | `ORDER_PENDING`, `USER_ACTIVE`              |
| Archivos           | `kebab-case`                       | `user-service.ts`, `user.controller.ts`     |
| Carpetas           | `kebab-case`                       | `user-management/`                          |

## TypeScript / JavaScript

- Las variables deben ser **descriptivas**: preferir `userId` sobre `id`, `userEmail` sobre `email`.
- Usar **verbos** para funciones y métodos: `getUser`, `createOrder`, `deleteSession`.
- Los booleanos deben empezar con `is`, `has`, `can` o `should`: `isActive`, `hasPermission`.
- Los arrays deben estar en plural: `users`, `orderItems`.
- Los handlers de eventos llevan el prefijo `handle`: `handleClick`, `handleSubmit`.

## Componentes (React / Vue / Angular)

- Nombre del componte en `PascalCase`: `UserCard`, `ProductList`.
- El archivo del componente coincide con el nombre: `UserCard.tsx`, `ProductList.vue`.
- Los componentes de página o vista llevan el sufijo `Page` o `View`: `DashboardPage`, `LoginView`.

## API / Rutas HTTP

- Rutas en `kebab-case` y plural: `/api/users`, `/api/order-items`.
- Nunca incluir el verbo en la ruta: usar `/users/:id` en vez de `/getUserById`.

## Base de datos

- Tablas en `snake_case` y plural: `user_accounts`, `order_items`.
- Columnas en `snake_case`: `created_at`, `user_id`.
- Claves foráneas: `{tabla_singular}_id` → `user_id`, `product_id`.
