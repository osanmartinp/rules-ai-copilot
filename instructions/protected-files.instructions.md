---
applyTo: "**"
---

# Archivos y carpetas protegidas

El agente **NUNCA** debe modificar, eliminar ni sobreescribir los siguientes archivos o carpetas sin confirmación **explícita y por escrito** del usuario.

---

## Configuración de entorno

- `.env`
- `.env.local`
- `.env.production`
- `.env.staging`
- `*.pem`, `*.key`, `*.crt` — certificados y claves privadas

## Infraestructura y despliegue

- `docker-compose.yml`
- `docker-compose.prod.yml`
- `Dockerfile` (cualquiera)
- `terraform/` (toda la carpeta)
- `kubernetes/` (toda la carpeta)
- `.github/workflows/` (pipelines de CI/CD)

## Base de datos

- `migrations/` — scripts de migración
- `seeds/` — datos semilla de producción
- Cualquier archivo con `schema` en el nombre que no sea de desarrollo

## Configuración del proyecto

- `package.json` — solo agregar dependencias si el usuario lo pide explícitamente
- `tsconfig.json`
- `.eslintrc.*`, `.prettierrc.*`
- `vite.config.*`, `webpack.config.*`, `next.config.*`

## Este repositorio

- `.github/copilot-instructions.md`
- `instructions/*.instructions.md`
- `prompts/*.prompt.md`

---

## Procedimiento ante duda

Si el agente no está seguro de si un archivo está protegido, debe **preguntar antes de modificarlo**.
