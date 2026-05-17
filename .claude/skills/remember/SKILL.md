---
name: remember
description: Guarda una memoria de largo plazo en memory/MEMORY.md cuando aprendes algo nuevo sobre el usuario que será útil en sesiones futuras. Invocar cuando el usuario te corrija, te explique cómo prefiere trabajar, mencione una decisión recurrente, o cuando notes un patrón en su workflow que podrías olvidar.
---

# Skill: remember

Append-ea una memoria nueva a `memory/MEMORY.md` con la fecha de hoy y la categoría correspondiente.

## Cuándo invocar

- El usuario te corrige: "no es así, yo prefiero X."
- El usuario explica un patrón de trabajo: "yo siempre arranco con Y."
- Aprendes algo sobre el usuario que va a aplicar a futuro: "uso métricas trimestrales", "rechazo tono hype", "siempre escribo en español, sin importar el contexto".
- Una decisión que el usuario ha repetido dos o más veces.

## Cuándo NO invocar

- **Información sensible** (passwords, tokens, API keys, datos privados de clientes). Nunca.
- Hecho de la conversación actual que no aplica a futuro.
- Detalle específico de un archivo (eso va en el archivo, no en `MEMORY.md`).
- Cosas obvias del contexto del repo (estructura de carpetas, convenciones del template).

## Cómo guardar

Append al final de `memory/MEMORY.md`, debajo de la línea `<!-- Las nuevas memorias se añaden debajo de esta línea -->`, con este formato:

```
- [YYYY-MM-DD] [categoría]: descripción específica
```

Categorías permitidas:

- `preferencia` — cómo prefiere trabajar
- `corrección` — algo que el usuario te corrigió
- `contexto` — hecho persistente sobre el usuario o sus proyectos
- `decisión` — decisión recurrente

Ejemplos válidos:

```
- [2026-05-20] preferencia: prefiere markdown sobre PDFs para drafts.
- [2026-05-21] contexto: trabaja en una fintech, métricas son trimestrales (Q1-Q4).
- [2026-05-22] corrección: cuando dice "reporte" se refiere a un doc ejecutivo de 1 página, no un análisis largo.
- [2026-05-25] decisión: rechaza tono hype en todo lo que escribe; pide trade-offs explícitos.
```

## Después de guardar

Decile al usuario, en una línea:

> "Lo guardé en `MEMORY.md`."

No expliques qué guardaste a menos que el usuario pregunte — la línea es suficiente.

## Cuando MEMORY.md crece mucho

Si `MEMORY.md` ya tiene más de ~80 memorias, sugiérele al usuario una poda. No podes vos solo.
