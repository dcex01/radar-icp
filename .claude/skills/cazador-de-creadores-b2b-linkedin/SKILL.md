---
name: cazador-de-creadores-b2b-linkedin
description: Encuentra y filtra creadores cuya audiencia contiene el cliente ideal, y devuelve una lista corta con la cadencia de publicación de cada uno y el motivo de descarte del resto. Úsala al montar la vigilancia o al revisarla, tras invocar modelador-de-icp.
---

# Cazador de creadores B2B

Buscas creadores **cuya audiencia contiene a tu cliente ideal**. No creadores
interesantes, ni influyentes, ni con muchos seguidores.

## El error que hay que evitar

El creador más grande del nicho suele ser el peor objetivo.

Corey Quinn tiene una audiencia enorme de FinOps. Casi toda es estadounidense,
y buena parte son ingenieros y consultores del propio gremio — es decir, tus
competidores, no tus clientes. Un post suyo con 800 comentarios puede rendir cero
contactos chilenos con poder de firma.

Un AWS User Group de Santiago con 200 comentarios al mes puede rendir cinco.

**El criterio es solapamiento con el ICP, no tamaño.** Un creador mediano y local
gana a uno enorme y remoto casi siempre.

## Conectores

| Plataforma | Conector | Herramientas |
|---|---|---|
| LinkedIn | **ConnectSafely** | `search-people-v2`, `search-posts-v2`, `get-latest-posts`, `get-profile`, `get-company-details` |
| Otras (X, YouTube, blogs, newsletters) | **Apify** | `search-actors` y luego `call-actor` |

Detalle en `reference/conectores.md`. Nombra el conector en cada paso que ejecutes.

⚠️ ConnectSafely opera **sobre la cuenta propia del usuario**, con topes diarios
propios. Las lecturas no los consumen apenas; las escrituras sí. Esta skill **solo
lee**.

## Procedimiento

1. **Carga la consulta** de `modelador-de-icp` desde Notion. Sin ella, detente y
   pídela: sin criterio, "buen creador" no significa nada.
2. **Parte de las semillas** en `reference/semillas.md`, más las que dé el usuario.
3. **Expande** desde cada semilla: quién comenta *sus* posts con autoridad, a quién
   citan, qué grupos y eventos aparecen. La expansión suele dar los mejores
   candidatos locales, que ninguna búsqueda por palabra clave encuentra.
4. **Mide cada candidato** con las cuatro pruebas de abajo.
5. **Descarta con motivo escrito.** Un descarte sin motivo se vuelve a evaluar en
   tres meses y se pierde el trabajo.
6. **Registra la cadencia** de cada superviviente. Es el dato operativo del sistema.
7. **Deja lista corta y descartes en Notion**, con fecha de revisión.

## Las cuatro pruebas

Ninguna es aprobar/reprobar por sí sola, salvo la primera.

1. **Solapamiento de audiencia** — de los últimos ~50 que comentaron, ¿cuántos
   pasarían las exclusiones y el rol decisor del ICP? Es la prueba que manda.
   **Bajo un 5%, se descarta**, por grande que sea.
2. **Cadencia** — ¿publica lo bastante seguido para vigilarlo? Sin publicación no
   hay comentarios que minar.
3. **Calidad del comentario** — ¿la gente escribe frases con contenido, o "Great
   post!" y emojis? Un hilo de aplausos no tiene señal de dolor.
4. **Tema** — ¿sus posts provocan comentarios donde alguien revela el problema?
   Un post motivacional de un técnico no sirve; uno sobre facturas de AWS sí.

Criterios de descarte con sus motivos tipo en `reference/criterios-de-descarte.md`.

## La cadencia es el reloj del sistema

Para cada creador de la lista corta, registra en Notion:
- **Frecuencia** — posts por semana, medida sobre los últimos 30 días, no declarada.
- **Última publicación** — fecha.
- **Ventana útil** — cuántos días tras publicar sigue llegando comentario nuevo.

**El "cuándo" del negocio sale de aquí, no de la hora del disparador.** La Routine
de los lunes dispara; esta cadencia decide a quién mirar y si hay algo nuevo. Un
creador que publica una vez al mes no se revisa cada lunes.

## Salida

**Lista corta** — nombre, URL, plataforma, solapamiento estimado (con la muestra que
lo respalda), cadencia, ventana útil, por qué entra.

**Descartados** — nombre, URL, motivo en una frase, fecha. Se conservan: el descarte
es trabajo hecho.

## Lo que no haces

- **No sigues, no conectas, no comentas.** Esta skill solo lee.
- **No inventas métricas de audiencia.** Si no mediste el solapamiento, dilo; no lo
  estimes de memoria.
- **No descartas por tamaño ni por idioma** sin medir el solapamiento primero.
