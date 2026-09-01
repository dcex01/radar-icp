---
name: clasificador-de-senales-de-dm-de-linkedin
description: Clasifica las respuestas recibidas en DMs de LinkedIn en tipos de señal y propone la acción siguiente para cada una, sin ejecutarla. Se invoca a mano tras revisar la bandeja; no tiene disparador automático en este montaje.
---

# Clasificador de señales de DM

Lees las respuestas que llegaron al outreach y las clasificas, para que el trabajo
de responder se ordene por lo que cada una necesita.

## Se invoca a mano

**Esta skill no tiene Routine propia**, por decisión de diseño: el volumen de
respuestas no lo justifica todavía.

⚠️ **Si el volumen supera unas decenas por semana, dilo.** Ese es el momento de
montarle un disparador diario aparte. No lo montes por iniciativa propia: avísalo.

## No respondes

Clasificas y **propones** la respuesta. No envías nada.

Una respuesta a un DM sale al mundo igual que el primer contacto, y necesita la
misma aprobación explícita. La tentación es mayor aquí, porque contestar a alguien
que ya escribió parece inofensivo. No lo es: un "gracias, te comparto material" mal
puesto quema un contacto bueno.

## Las clases

Seis. Detalle y frases-señal en `reference/taxonomia.md`.

| Clase | Qué es | Urgencia |
|---|---|---|
| **Interés real** | Pregunta, cuenta su contexto, pide detalles | Alta — responder en 24h |
| **Interés tibio** | Cortesía con apertura ("interesante, ya veremos") | Media |
| **Objeción** | Interés con freno: precio, momento, proveedor actual | Alta — es interés, no rechazo |
| **Derivación** | Manda a otra persona o área | Alta — es un sí con ruta |
| **Rechazo** | No, claro | Cerrar bien |
| **Fuera de ICP** | Responde pero no es cliente: proveedor, candidato, estudiante | Baja |

## Las dos que se leen mal

**La objeción no es rechazo.** "Ahora estamos con otro proveedor" es alguien que
tiene el problema, ya invirtió en resolverlo, y te está diciendo cuándo volver.
Tratarla como un no pierde el contacto más calificado del lote.

**La derivación es la mejor señal del sistema.** "Habla con {nombre}, que ve
infraestructura" significa que la persona validó que el problema existe y te dio el
nombre de quien lo sufre. ⚠️ Escribir a esa persona sigue necesitando aprobación, y
el mensaje debe **mencionar quién te derivó** — sin eso es un contacto frío más.

## El rechazo se cierra bien

Una frase, sin insistir, sin preguntar por qué. Se registra en Notion como
**no contactar**, y se respeta.

Insistir tras un no convierte un rechazo en un bloqueo, y un bloqueo cuesta mucho
más: afecta la salud de la cuenta desde la que opera todo el sistema.

## Procedimiento

1. Trae las respuestas con **ConnectSafely** (`list-conversations`,
   `get-conversation-messages`).
2. Cruza con el histórico de Notion para saber qué borrador originó cada hilo.
   **Una respuesta sin su mensaje original no se puede clasificar bien.**
3. Clasifica cada una, citando la frase que sostiene la clase.
4. Propón acción según `reference/acciones-por-clase.md`.
5. Actualiza el estado en Notion.
6. **Detente.** Presenta lo clasificado para aprobación.
7. Si son más de unas 25 en la semana, **plantea montar el disparador diario**.

## Lo que no haces

- No respondes ni envías.
- No escribes a un derivado sin aprobación.
- No reclasificas un rechazo como objeción para reintentar. Si dijo no, es no.
