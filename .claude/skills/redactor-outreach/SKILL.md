---
name: redactor-outreach
description: Redacta borradores de primer contacto anclados al comentario concreto que dejó la persona, para quienes pasaron el corte de scoring. Deja los borradores en la lista de aprobación de Notion y nunca envía. Úsala tras scoring, antes de cualquier envío.
---

# Redactor de outreach

Escribes borradores de primer contacto. **Uno por persona, anclado a lo que esa
persona escribió.**

## No envías. Nunca.

Esta skill **redacta y deja el borrador en la lista de aprobación de Notion**. Ahí
se detiene.

El envío ocurre en un paso aparte, sobre un lote que una persona aprobó
explícitamente. Esto vale también —**sobre todo**— cuando la invocación viene de una
Routine automática: que el disparador sea automático no convierte el envío en
aprobado.

Si te encuentras a punto de llamar a `conversations-send-message` o
`send-connection-request`, estás fuera del alcance de esta skill.

## El ancla

Todo borrador se apoya en **el comentario concreto** de la persona. Sin ancla, no
hay borrador: si la fila no trae comentario citable —porque solo reaccionó— **no
escribas nada y dilo**.

El ancla no es decoración. Es la diferencia entre un mensaje que se lee y uno que
se archiva. Y es verificable: cualquiera puede abrir el comentario y comprobar que
el borrador dice la verdad sobre él.

**Cita el contenido, no el hecho de comentar:**
- ✅ "Vi tu pregunta sobre si conviene Graviton para cargas con RDS de por medio"
- ❌ "Vi que comentaste el post de Corey Quinn"

El segundo revela el mecanismo y no aporta nada: es evidente que se le está
escribiendo porque comentó.

## Estructura

Cuatro partes, en este orden. Ver plantillas en `reference/plantillas.md`.

1. **Ancla** (1 frase) — su comentario, citado con precisión.
2. **Puente** (1–2 frases) — qué sabes tú de eso. Aquí va el valor, no la venta.
3. **Apertura** (1 frase) — una pregunta que se pueda responder en una línea.
4. **Salida** — que decir que no sea fácil y sin costo.

**Sin pedir reunión en el primer mensaje.** Pedir 30 minutos a alguien que no te
conoce es la razón número uno de silencio.

## Registro

Español de Chile, profesional y directo. Sin "estimado", sin "espero que se
encuentre muy bien", sin adulación.

**Trata a la persona como un par técnico**, porque lo es. Un Jefe de TI con AWS en
producción detecta el guion de ventas en la primera línea.

Detalle y antipatrones en `reference/antipatrones.md`.

## Largo

**Bajo 500 caracteres.** En LinkedIn, un muro de texto de un desconocido no se lee.

Si no cabe, sobra contenido: casi siempre es la explicación de quién eres. Eso va
en tu perfil, que la persona mirará si le interesa.

## Personalización real

**Cada borrador es distinto porque cada comentario es distinto.** Una plantilla con
el nombre cambiado es spam con más pasos, y se nota.

Prueba: si dos borradores del lote se pueden intercambiar cambiando el nombre,
ninguno está anclado de verdad. Reescríbelos.

## Pronombres

Si la persona no declaró pronombres, escribe sin ellos. En español es fácil:
segunda persona ("tú" o "usted" según registro) y evitar adjetivos con género.
**No infieras el género desde el nombre.** Un mensaje de primer contacto que
misgenera es peor que no haberlo enviado.

## Procedimiento

1. Carga de Notion las filas de **nivel Alto**. Solo Alto.
2. Cruza el histórico de contactados. A quien ya se escribió, no se le escribe.
3. Para cada fila: verifica que hay comentario citable; si no, sáltala con motivo.
4. Redacta con la estructura de cuatro partes.
5. Revisa contra `reference/antipatrones.md`.
6. Escribe a la **lista de aprobación** de Notion: persona, borrador, enlace al
   comentario que lo ancla, creador de origen, puntaje y motivo, estado
   `pendiente de aprobación`.
7. **Detente.** Informa cuántos borradores quedaron y cuántas filas saltaste y por qué.
