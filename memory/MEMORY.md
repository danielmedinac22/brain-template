# MEMORY

Este archivo es la memoria persistente del agente sobre ti, el usuario.

Claude lo lee al inicio de cada sesión antes de hacer cualquier cosa. Cuando aprende algo nuevo sobre cómo prefieres trabajar, te corrige, o nota un patrón, lo append-ea aquí con el skill `remember`.

## Cómo está organizado

Cada memoria es una línea con el formato:

```
- [YYYY-MM-DD] [categoría]: descripción específica
```

Categorías:

- **preferencia** — cómo prefieres trabajar
- **corrección** — algo que el agente entendió mal y tú corregiste
- **contexto** — hecho persistente sobre ti o tus proyectos
- **decisión** — decisión recurrente que has tomado

## Poda

Cada dos meses, abre este archivo y borra lo que ya no aplica. No es trabajo del agente — es tuyo. La memoria útil es la curada, no la acumulada.

## Memorias

> Por ahora vacío. Las primeras memorias aparecerán cuando empieces a usar el brain.

<!-- Las nuevas memorias se añaden debajo de esta línea -->
