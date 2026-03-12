---
applyTo: "**"
---

# Convenciones de nomenclatura

Aplicar en todo el código generado o modificado.

---

## General

| Elemento           | Convención        | Ejemplo                        |
|--------------------|-------------------|--------------------------------|
| Variables          | `camelCase`       | `userEmail`, `totalPrice`      |
| Constantes         | `UPPER_SNAKE_CASE`| `MAX_RETRIES`, `API_BASE_URL`  |
| Funciones          | `camelCase`       | `getUserById`, `formatDate`    |
| Clases             | `PascalCase`      | `UserService`, `PaymentGateway`|
| Interfaces / Types | `PascalCase`      | `UserDto`, `ApiResponse`       |
| Enums              | `PascalCase`      | `OrderStatus`, `UserRole`      |
| Archivos           | `kebab-case`      | `user-service.ts`, `api-client.ts` |
| Carpetas           | `kebab-case`      | `user-management/`, `api-clients/` |

## TypeScript / JavaScript

- Usar **verbos** para funciones: `getUser`, `createOrder`, `deleteSession`.
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
