---
name: modelador-de-icp
description: Convierte una descripción en prosa del cliente ideal en una consulta estructurada y verificable, que el resto del sistema usa como criterio único. Úsala al definir o revisar el ICP, y siempre antes de cazar creadores o puntuar personas.
---

# Modelador de ICP

Tomas una descripción en prosa — imprecisa, con supuestos implícitos — y devuelves
una **consulta de cliente ideal**: un objeto con dimensiones nombradas, cada una con
señales observables y su forma de verificación.

El resto del sistema no vuelve a leer la prosa. Lee esta consulta. Si la consulta
está mal, todo lo que sigue está mal en silencio.

## El principio que gobierna todo

**Cada criterio debe ser verificable desde lo que un conector puede traer.**

"Empresas con cargas productivas en AWS" no es verificable desde un perfil de
LinkedIn. "La persona menciona AWS, EC2, RDS o costos cloud en su titular, su
experiencia o el comentario que dejó" sí lo es.

Cuando un criterio del usuario no sea verificable, no lo descartes: **tradúcelo a
su proxy observable y marca la traducción explícitamente**, para que quien lea la
consulta sepa que es un proxy y no el hecho.

## Dimensiones

Toda consulta tiene estas seis. Ninguna se omite; si una no aplica, se escribe
"sin restricción" y se dice por qué.

1. **Firmografía** — tamaño, tipo de organización (privada, pública), industria.
2. **Señal técnica** — qué indica que la empresa tiene el problema que resuelves.
3. **Rol decisor** — quién firma. Cargos concretos, no "tomadores de decisión".
4. **Geografía** — países, con su forma de detección (ubicación declarada, idioma
   del comentario, empresa con presencia local).
5. **Exclusiones** — a quién descartar aunque puntúe alto. Competidores, proveedores,
   estudiantes, buscadores de empleo, reclutadores.
6. **Señal de dolor** — qué diría alguien, en un comentario, que revela el problema.

Ver `reference/dimensiones.md` para qué va y qué no va en cada una.

## Procedimiento

1. **Lee la prosa entera antes de estructurar nada.** Los criterios más importantes
   suelen ir implícitos en una subordinada.
2. **Separa hecho de deseo.** "Mi cliente ideal tiene AWS en producción" es un hecho
   a verificar. "Ojalá fueran empresas grandes" es una preferencia: va como peso, no
   como filtro duro.
3. **Traduce cada criterio a señal observable.** Marca los proxies con `(proxy)`.
4. **Pregunta lo que falte.** No inventes exclusiones, ni geografías, ni cargos que
   el usuario no nombró. Si la prosa no dice nada sobre tamaño de empresa, la
   dimensión se escribe "sin restricción — no especificado", y lo dices.
5. **Emite en el formato de `reference/plantilla-consulta.md`.**
6. **Guarda en Notion**, en la página de consulta de cliente ideal, con fecha.

## Lo que no haces

- **No inventas umbrales numéricos.** Esta skill define *qué* mirar. `scoring` define
  *cuánto pesa*, y sus cortes los pone la persona.
- **No amplías el ICP para que entre más gente.** Un ICP ancho no es un ICP.
- **No infieres el cargo desde el nombre, la foto ni el idioma.** Solo desde lo que
  la persona declara.

## Salida

Un documento con las seis dimensiones, cada criterio con su señal observable y su
método de verificación, más una sección `Preguntas abiertas` con lo que no pudiste
determinar sin inventar. Esa sección puede quedar no vacía: es preferible a
rellenarla con supuestos.

Ejemplo completo trabajado en `reference/ejemplo-finops-aws.md`.
