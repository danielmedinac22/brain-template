# El brain — instrucciones para Claude

Esta carpeta es un "brain": un espacio organizado donde el usuario guarda contexto, trabaja en proyectos, y produce outputs. Antes de hacer cualquier cosa, lee este archivo completo. Es el contrato.

## El contrato

Cuatro folders. Una regla por cada uno:

| Carpeta | Qué contiene | Tu rol |
|---|---|---|
| `input/` | Material recibido de afuera (notas, transcripciones, research, docs externos). | **Lectura libre.** No escribas aquí salvo que el usuario te lo pida explícitamente. |
| `work/` | Trabajo activo del usuario (drafts, PRDs, proyectos en curso). | **Lectura y escritura.** Es donde colaboras. |
| `output/` | Material listo para salir afuera (posts, reportes, contenido publicable). | **Escritura solo cuando el usuario haya validado lo que está en `work/`.** No "publiques" automáticamente — el usuario decide cuándo algo pasa de `work/` a `output/`. |
| `thinking/` | Ideas sueltas del usuario, sin destino. | **Lectura libre como contexto cruzado.** No escribas aquí salvo que el usuario lo pida. |

Si el usuario te pide algo y la carpeta destino es ambigua, pregúntale **una vez**. Después sigue el patrón.

## Memoria persistente

`memory/MEMORY.md` es el índice de lo que has aprendido sobre el usuario en sesiones anteriores. **Léelo al inicio de cada sesión** antes de cualquier otra acción.

Cuando el usuario te corrija, te explique cómo prefiere trabajar, o aprendas algo nuevo sobre cómo escribe o decide, **invoca el skill `remember`** para guardar la memoria.

**NO guardes información sensible** en `MEMORY.md`: passwords, tokens, API keys, datos privados de clientes. Si dudas, no lo guardes.

## Skills disponibles

Ver `.claude/skills/`. Cada skill tiene su propio `SKILL.md` con cuándo invocarla.

Vienen dos por defecto:
- `remember` — guarda memoria de largo plazo
- `process-transcript` — convierte una transcripción de reunión en un reporte

El usuario puede añadir más. Cuando lo haga, respeta la convención de un folder por skill con su `SKILL.md`.

## Reglas duras

- **No reorganices la estructura sin permiso explícito.** Si crees que falta una carpeta, propónlo, no lo hagas.
- **No mezcles archivos entre folders.** Un PRD draft no va en `output/`. Una transcripción cruda no va en `work/`.
- **No borres archivos del usuario sin confirmación.** Ni siquiera los temporales.
- **No inventes contenido para llenar archivos vacíos.** Si una sección no tiene info, déjala vacía o pregunta.
- **No publiques nada afuera (Slack, Notion, GitHub, email) sin confirmación explícita del usuario** — aunque el archivo esté en `output/`.

## Cómo nombrar archivos

- Drafts y outputs con fecha: `YYYY-MM-DD-<slug>.md`.
- Reportes derivados: `<fecha-original>-<tema>-reporte.md`.
- Notas sueltas en `thinking/`: nombre libre, descriptivo.

## Voz del usuario

> Este bloque lo personaliza el usuario. Si está vacío, pregúntale por su voz, su tono, su idioma preferido, y guarda la respuesta aquí.

- **Idioma:** español (default — confirmar con el usuario)
- **Tono:** _por definir_
- **Formato favorito:** markdown
- **Anti-patrones:** _por definir_

---

**Última revisión:** template inicial. Edita esto cuando cambies la estructura.
