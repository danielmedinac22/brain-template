# Brain — template para Claude Code

Este es el template del "brain" que muestro en el video [Cómo armar un brain con Claude Code](#) (link al video pendiente).

Es una **carpeta de proyectos, pero con superpoderes**: vive un agente de Claude Code adentro que entiende cómo está organizada y trabaja con tus archivos como contexto.

## Cómo usarlo

```bash
git clone https://github.com/[usuario]/brain-template mi-brain
cd mi-brain
claude
```

Claude lee el `CLAUDE.md` raíz cuando arranca y aprende el contrato del brain antes de hacer cualquier cosa.

Si no quieres clonar, también puedes crearlo desde cero pidiéndole a Claude:

> "Armame un brain con esta estructura: input, work, output, thinking. Crea un README en cada una y un CLAUDE.md raíz que le explique al agente cómo respetar el contrato. Que sea opinado, no genérico."

En el video muestro los dos caminos.

## La estructura

- **`input/`** — lo que llega de afuera. Notas de reunión, transcripciones, research, inspiración, documentos que ya tenías. _Si lo recibiste, va aquí._
- **`work/`** — lo que estás construyendo ahora. Drafts, PRDs, proyectos en curso. _Si lo estás editando esta semana, va aquí._
- **`output/`** — lo que va a salir afuera. Posts, reportes, contenido para publicar. _Si va a salir a alguien más, va aquí._
- **`thinking/`** — el cajón de pensar en voz alta. Ideas que rebotas, notas sin destino. _Opcional pero útil._
- **`memory/MEMORY.md`** — lo que el agente aprende sobre ti entre sesiones (cómo escribes, qué prefieres, decisiones recurrentes).
- **`.claude/skills/`** — workflows que Claude puede aplicar. Vienen dos de muestra.

## Skills incluidos

| Skill | Qué hace |
|---|---|
| `remember` | Guarda una memoria de largo plazo en `memory/MEMORY.md` cuando Claude aprende algo nuevo sobre ti. Se invoca automáticamente cuando lo corriges o le explicas un patrón. |
| `process-transcript` | Lee una transcripción de reunión de `input/` y genera un reporte ejecutivo en `output/` con decisiones, próximos pasos, riesgos y preguntas pendientes. Pídele "procesame esta transcripción". |

Modifícalos, elimínalos, escribe los tuyos. El siguiente video de la serie es sobre cómo construir skills propios.

## Lo que NO viene

- Tu información. Empiezas con el brain vacío y lo vas llenando.
- MCPs. Si quieres conectar Notion, Slack, calendario, los agregas tú.
- Más skills. La idea es empezar con dos, no con doce.

## Trade-offs (los mismos del video)

- **Sin ritual de limpieza, esto se convierte en basurero ordenado.** Cada cierto tiempo, vacía `input/` de lo que ya procesaste y mueve a `output/` lo que ya publicaste.
- **Cuatro folders se va a sentir poco.** Vas a querer añadir "reference", "archive", "templates". Pruébalo con cuatro primero. Si después de un mes te falta algo, añádelo — pero con razón concreta, no con intuición.
- **`MEMORY.md` crece.** Cada dos meses, ábrelo y borra lo que ya no aplica. No es trabajo del agente. Es tuyo.

## Personalízalo

Si quieres que el agente use la estructura distinto:

1. Edita `CLAUDE.md` raíz con tus reglas.
2. Pídele a Claude: "actualiza los READMEs de cada carpeta para reflejar mis cambios en `CLAUDE.md`."

## Licencia

MIT. Forkéalo, modifícalo, compártelo. Si construyes algo encima, mándamelo — me interesa ver qué hacen con esto.
