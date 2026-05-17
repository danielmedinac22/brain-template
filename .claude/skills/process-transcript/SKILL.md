---
name: process-transcript
description: Lee una transcripción de reunión en input/ y genera un reporte ejecutivo estructurado en output/ con decisiones, próximos pasos, riesgos y preguntas pendientes. Usar cuando el usuario diga "procesame esta transcripción", "hazme el reporte de esta reunión", o cuando arrastre un archivo de transcripción al brain.
---

# Skill: process-transcript

Convierte una transcripción de reunión (de Granola, Otter, Zoom, Notion AI, cualquiera) en un reporte ejecutivo accionable.

## Inputs esperados

- Una transcripción en `input/`. Formato libre — markdown, texto plano, lo que tenga.
- Opcional: el usuario indica el nombre del archivo. Si no, listas las transcripciones disponibles en `input/` y le preguntas.

## Output

Un archivo nuevo en `output/<fecha-reunión>-<tema>-reporte.md` con exactamente estas cuatro secciones:

```markdown
# <Tema> — Reporte

**Fecha de la reunión:** YYYY-MM-DD
**Asistentes:** <lista corta>

## Decisiones tomadas

- ...

## Próximos pasos

### <Persona 1>
- ...

### <Persona 2>
- ...

## Riesgos identificados

- ...

## Preguntas pendientes

- ...
```

## Reglas

1. **Solo extraer lo que está en la transcripción.** NO inventes acciones, fechas, ni asistentes que no estén mencionados. Si la transcripción no nombra a una persona, no la inventes.
2. **Si una sección queda vacía, escribe "(ninguna identificada)".** No la elimines.
3. **Nombrar el archivo:** `<fecha-reunión>-<tema-slug>-reporte.md` (ej: `2026-05-20-roadmap-q2-reporte.md`). Si la fecha de la reunión no es clara, usa la fecha de hoy + nota al inicio del archivo.
4. **Tono:** ejecutivo, conciso. Una decisión = una línea. Un próximo paso = una línea con verbo de acción al inicio.
5. **No interpretes intención.** Si alguien "mencionó que quizás" haría algo, NO lo conviertes en un próximo paso. Va a "Preguntas pendientes".

## Después de generar

Reporta al usuario:

- Ruta del archivo creado (relativa al brain).
- Cantidad de bullets en cada sección.
- Si alguna sección quedó vacía, menciónalo.

Ejemplo de mensaje al usuario:

> "Listo. `output/2026-05-20-roadmap-q2-reporte.md`. 4 decisiones, 7 próximos pasos repartidos entre 3 personas, 2 riesgos, 3 preguntas abiertas."

## Cuando la transcripción es ambigua

Si después de leer la transcripción no podés identificar al menos una decisión o un próximo paso, no inventes uno para llenar. Reporta al usuario que la transcripción parece más exploratoria que decisional, y preguntale si querés generar un reporte de "discusión" en vez de uno ejecutivo.
