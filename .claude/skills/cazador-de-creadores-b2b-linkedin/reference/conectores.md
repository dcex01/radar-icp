# Conectores, herramienta por herramienta

## ConnectSafely — LinkedIn

Opera sobre **la cuenta de LinkedIn del propio usuario**, con su sesión autenticada.
Devuelve lo que el usuario ya vería estando conectado. Topes diarios propios,
aplicados del lado del servidor.

### Lectura (lo que usa esta skill)
| Para | Herramienta |
|---|---|
| Buscar creadores por tema | `search-posts-v2`, `search-people-v2` |
| Últimos posts de un creador | `get-latest-posts` |
| Quién comentó | `get-all-post-comments` |
| Quién reaccionó | `get-post-reactions-v2` |
| Perfil de un comentarista | `get-profile` |
| Empresa de un comentarista | `get-company-details` |
| Grupos y sus miembros | `search-groups`, `get-group-members` |
| Asistentes a un evento | `get-event-attendees` |

⚠️ **`get-all-post-comments` frente a `get-post-comments`:** la primera pagina el
hilo completo. En un post con cientos de comentarios, la segunda devuelve solo el
primer tramo y **la muestra queda sesgada hacia los comentarios más tempranos y
mejor posicionados** — que no son los más relevantes. Usa la completa.

### Escritura (esta skill NO la usa)
`send-connection-request`, `conversations-send-message`, `comment-on-post`,
`follow-user`, `react-to-post`. Solo tras aprobación humana explícita, y en el paso 8.

### Ritmo
Entre escrituras, 30–90 segundos, variados. Nunca en ráfaga. Las lecturas no
necesitan pausa.

## Apify — el resto de plataformas

Marketplace de scrapers ("Actors"). No hay un Actor fijo: **búscalo cada vez**, porque
cambian de mantenedor y de calidad.

1. `search-actors` con la plataforma y lo que buscas.
2. `fetch-actor-details` para leer el README y el esquema de entrada **antes** de
   ejecutar. Ejecutar sin leer el esquema es la causa más común de un run vacío.
3. `call-actor` con la entrada correcta.
4. `get-dataset-items` para los resultados.

**Preferir Actors con más uso y mejor valoración.** Un Actor abandonado devuelve
datos parciales sin marcar el error, que es peor que fallar.

### Qué plataforma con qué
- **X/Twitter, YouTube, Reddit** — Apify.
- **Newsletters y blogs** — Apify, o `WebFetch` si es una página pública simple.
- **LinkedIn** — **siempre ConnectSafely, nunca Apify.** Los scrapers de LinkedIn
  operan sin la sesión del usuario y son la vía rápida a un bloqueo de cuenta.

## Notion
`notion-create-pages`, `notion-update-page`, `notion-query-data-sources` para leer
la consulta y escribir listas.
