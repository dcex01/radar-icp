# Dónde escribe cada skill

Las páginas de control viven en Notion, bajo la página raíz **Radar ICP**.
Estos son los identificadores que las skills necesitan para leer y escribir.

## Página raíz

**Radar ICP** — `3ce18f68-a0bf-81ec-913d-f6981d08c37d`
https://app.notion.com/p/3ce18f68a0bf81ec913df6981d08c37d

⚠️ Creada como página privada a nivel de workspace. Si hay que compartirla con
alguien más, moverla a un teamspace primero.

## Consulta de cliente ideal (página)

`3ce18f68-a0bf-811d-90ec-d2b9e6fb28ff`
https://app.notion.com/p/3ce18f68a0bf811d90ecd2b9e6fb28ff

La escribe `modelador-de-icp`. **También guarda los umbrales de `scoring`**, en su
propia sección. Es la fuente de verdad de los cortes: si esa sección está vacía,
`scoring` pregunta y se detiene.

## Bases de datos

| Base | data_source_id | La escribe |
|---|---|---|
| Creadores vigilados | `d32bbc6d-218b-4ff2-9d64-eb7fa7995058` | `cazador-de-creadores-b2b-linkedin` |
| Personas puntuadas | `ced6d709-ba5c-43ad-8282-b4ddb92dee5f` | `scoring` |
| Aprobación de borradores | `ccaf1460-a351-4839-96ee-38a3e3f423d3` | `redactor-outreach` |
| Histórico de contactados | `e21b5007-a03a-4276-8b92-b7d3c3406951` | envío + `clasificador-de-senales-de-dm-de-linkedin` |

Para leer un esquema completo, pasar el `collection://<data_source_id>` a
`notion-fetch`.

## Cómo se relacionan

```
Creadores vigilados
  └─ Personas puntuadas        (Creador origen ⇄ Personas puntuadas)
       ├─ Aprobación           (Persona ⇄ Borradores)
       └─ Histórico            (Ficha ⇄ Contactos)
```

Las relaciones son de doble vía: desde la ficha de un creador se ve a quién rindió,
y desde una persona se ve su borrador y su historial.

## Los dos cruces obligatorios

**`scoring` cruza contra el Histórico antes de proponer a nadie.** Alguien ya
contactado no vuelve a la lista salvo señal nueva y más fuerte. Escribir dos veces a
la misma persona por dos creadores distintos es la forma más rápida de parecer un bot.

**`Estado = No contactar` en el Histórico es permanente.** `scoring` debe excluir a
esa persona en todas las rondas futuras, venga del creador que venga.

## Campos que no pueden quedar vacíos

| Base | Campo | Por qué |
|---|---|---|
| Creadores vigilados | `Motivo` | Un descarte sin motivo se re-evalúa en tres meses y se repite el trabajo |
| Personas puntuadas | `Motivo` | Una puntuación sin motivo es inauditable |
| Aprobación | `Ancla` | Sin comentario citable no hay borrador |
| Histórico | `Frase que sostiene la clase` | Sin la cita, la clasificación no se puede revisar |
