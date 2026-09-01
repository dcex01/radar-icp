---
name: scoring
description: Puntúa a las personas que interactuaron con un post contra la consulta de cliente ideal, y devuelve una lista priorizada con nivel y motivo por fila. Exige que los umbrales de corte lleguen como entrada; si faltan, pregunta y se detiene. Úsala tras recolectar quién comentó y antes de redactar nada.
---

# Scoring

Conviertes una lista cruda de personas que interactuaron en una lista priorizada,
donde **cada fila lleva su motivo**.

## Los umbrales no se inventan. Nunca.

Esta skill **no fija los cortes**. Los recibe: desde la página de Notion, o
preguntándolos a la persona.

**Si no están, pregunta y detente.** No los deduzcas, no uses "un valor razonable",
no copies los del ejemplo de `reference/umbral.md`.

Un umbral inventado no produce un error visible. Produce una lista que **parece
rigurosa**, que se aprueba sin discusión, y que hace escribir a la gente equivocada.
El daño aparece semanas después, como una tasa de respuesta mala que nadie sabe
explicar. Es el fallo más caro del sistema entero y el más difícil de detectar.

Lo mismo para los **pesos** de cada dimensión.

## Un motivo por fila, siempre

Una puntuación sin motivo es inauditable. Con motivo, la persona puede leer diez
filas y detectar que el criterio está mal calibrado. Sin él, solo ve números y los
acepta.

**El motivo cita la evidencia**, no la repite en abstracto:
- ✅ "Jefe de Infraestructura en {empresa}; el comentario pregunta por Savings Plans
  vs Reserved para su flota de RDS"
- ❌ "Alto encaje con el ICP"

## Evidencia, no inferencia

Puntúa **solo lo que la persona declara** o lo que dice su comentario.

**Prohibido inferir:**
- El **género** desde el nombre o la foto. No se usa, no se registra, no influye.
- La **nacionalidad** desde el nombre o el apellido.
- La **seniority** desde la foto o la edad aparente.
- El **presupuesto** desde el tamaño aparente de la empresa.

Si un dato falta, la dimensión puntúa **cero por dato ausente**, y el motivo lo dice:
"sin ubicación declarada". Cero por ausencia no es lo mismo que cero por no encajar,
y la diferencia importa: el primero se puede resolver mirando el perfil completo.

Detalle en `reference/evidencia.md`.

## Procedimiento

1. **Carga la consulta** de cliente ideal desde Notion. Sin ella, detente.
2. **Carga umbrales y pesos.** Si faltan, pregunta y detente.
3. **Aplica primero las exclusiones.** Un excluido sale de la lista, no puntúa. Sale
   con motivo: "empleado de {competidor}".
4. **Puntúa cada dimensión** con su evidencia citada.
5. **Suma con los pesos dados.**
6. **Asigna nivel** con los umbrales dados.
7. **Escribe a Notion**: persona, URL, nivel, puntaje, motivo, evidencia, creador de
   origen, enlace al comentario, fecha.
8. **Reporta la distribución.** Si el 80% cae en un nivel, los umbrales están mal
   calibrados. Dilo — no es tu decisión arreglarlo, pero sí avisarlo.

## Dimensiones

Las mismas seis del ICP, más una que solo existe aquí:

7. **Calidad de la interacción** — qué hizo la persona. Un comentario sustantivo
   pesa mucho más que una reacción. Ver `reference/dimensiones-y-pesos.md`.

⚠️ **Una reacción sin comentario casi no es señal.** Es el error más común: inflar
la lista con gente que solo dio "me gusta". Si el volumen obliga a elegir, los
comentaristas primero.

## Deduplicación

Antes de escribir, cruza contra el histórico de contactados en Notion.

Alguien ya contactado **no vuelve a la lista** salvo que haya señal nueva y más
fuerte. Escribir dos veces a la misma persona por dos creadores distintos es la
forma más rápida de parecer un bot.

## Lo que no haces

- **No escribes mensajes.** Eso es `redactor-outreach`.
- **No contactas a nadie.**
- **No ajustas los umbrales** para que pase más gente, aunque la lista quede corta.
  Una lista corta es un resultado válido y es información.
