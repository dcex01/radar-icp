# radar-icp

Convierte los comentarios de creadores ajenos en LinkedIn (y otras plataformas) en
una lista de contacto puntuada. Claude orquesta; no hay motor externo.

## Las cinco skills

| Skill | Entrada | Salida |
|---|---|---|
| `modelador-de-icp` | Descripción en prosa del cliente ideal | Consulta de cliente ideal, estructurada |
| `cazador-de-creadores-b2b-linkedin` | La consulta | Lista corta de creadores + motivo de descarte del resto |
| `scoring` | Personas que interactuaron + la consulta + umbrales | Lista priorizada, con nivel y motivo por fila |
| `redactor-outreach` | Quien pasó el corte | Borrador anclado a su comentario. **No envía** |
| `clasificador-de-senales-de-dm-de-linkedin` | Respuestas recibidas | Clase de señal + acción sugerida |

## Cómo se invocan

Viven en `.claude/skills/`, así que son invocables con el tool `Skill` cuando abres
Claude Code **con este directorio como raíz**. Desde otro directorio son archivos
muertos. Para tenerlas en todos tus proyectos, cópialas a `~/.claude/skills/`.

## Conectores que usa

- **ConnectSafely** — LinkedIn: reacciones y comentarios de un post, perfiles,
  invitaciones y DMs. Opera sobre la cuenta propia, con sus topes diarios.
- **Apify** — el resto de plataformas.
- **Notion** — las páginas de control: consulta, creadores vigilados, personas
  puntuadas, lista de aprobación, histórico de contactados.

## Regla que no se negocia

Ninguna acción que salga al mundo — enviar un mensaje, aceptar una invitación —
ocurre sin aprobación humana explícita, tampoco cuando la dispare una Routine.
Las skills **redactan y proponen**; la persona aprueba.

## Los umbrales no se inventan

`scoring` exige que los umbrales de corte lleguen como entrada, desde Notion o desde
la persona. Si faltan, la skill pregunta y se detiene. Un umbral inventado produce
una lista que parece rigurosa y no lo es.
