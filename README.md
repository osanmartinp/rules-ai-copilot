# rules-ai-copilot

Repositorio de reglas y directrices para agentes de IA (GitHub Copilot, Claude, etc.) que asisten en el desarrollo de código. El objetivo es estandarizar el comportamiento del agente, aplicar buenas prácticas y proteger archivos o configuraciones críticas del proyecto.

---

## ¿Para qué sirve este repositorio?

Cuando un agente de IA te ayuda a programar, necesita contexto sobre cómo quieres que trabaje: qué convenciones seguir, qué archivos no debe modificar, qué patrones de código son preferidos y cuáles están prohibidos. Este repositorio centraliza todas esas reglas en forma de archivos `.instructions.md` y `.prompt.md` que el agente lee automáticamente.

---

## Estructura

```
rules-ai-copilot/
├── .github/
│   └── copilot-instructions.md   # Reglas globales que el agente siempre aplica
├── instructions/
│   ├── general.instructions.md   # Buenas prácticas generales de código
│   ├── protected-files.instructions.md  # Archivos y carpetas que el agente NO debe tocar
│   ├── naming.instructions.md    # Convenciones de nomenclatura
│   └── architecture.instructions.md    # Patrones y decisiones de arquitectura
├── prompts/
│   └── refactor.prompt.md        # Prompts reutilizables para tareas comunes
└── README.md
```

---

## Tipos de reglas

### Buenas prácticas
- Convenciones de código (nombres de variables, funciones, clases)
- Patrones de diseño preferidos
- Manejo de errores
- Escritura de tests

### Archivos protegidos
Archivos que el agente **nunca** debe modificar sin confirmación explícita:
- Archivos de configuración de entorno (`.env`, `.env.production`)
- Archivos de infraestructura (`docker-compose.yml`, `terraform/`)
- Scripts de migración de base de datos
- Archivos de CI/CD (`.github/workflows/`)

### Restricciones de arquitectura
- Capas que no deben mezclarse
- Dependencias prohibidas entre módulos
- Patrones de código a evitar

---

## Cómo usar estas reglas

### Con GitHub Copilot (VS Code)
Coloca el archivo principal de reglas en `.github/copilot-instructions.md`. Copilot lo lee automáticamente en cada sesión del workspace.

### Con archivos `.instructions.md`
Crea archivos `*.instructions.md` en el workspace o en `.github/instructions/`. Puedes usar el campo `applyTo` para restringir a qué archivos aplican:

```markdown
---
applyTo: "src/**/*.ts"
---

# Reglas para TypeScript
- Siempre usar tipos explícitos, nunca `any`
- Preferir `interface` sobre `type` para objetos
```

### Con archivos `.prompt.md`
Define prompts reutilizables para tareas recurrentes:

```markdown
---
mode: agent
---

Revisa el código seleccionado y aplica las reglas de este repositorio.
```

---

## Contribuir reglas nuevas

1. Crea un archivo en `instructions/` con el nombre del dominio que cubre.
2. Usa el frontmatter YAML para definir el alcance (`applyTo`).
3. Escribe las reglas en formato de lista clara y concisa.
4. Abre un PR describiendo qué problema resuelve la nueva regla.

---

## Referencias

- [VS Code — Copilot Instructions](https://code.visualstudio.com/docs/copilot/copilot-customization)
- [GitHub Copilot Customization Docs](https://docs.github.com/en/copilot/customizing-copilot)
