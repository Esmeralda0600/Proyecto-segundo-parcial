# Descricion de pantallas trivia Marvel


---

## Pantallas

### Pantalla 1 — Login (`/login`)

Página de acceso al cuartel. Punto de entrada para agentes registrados y nuevos reclutas.

#### Elementos de la interfaz

- **Título** `RECLUTAMIENTO AVENGERS` con efecto de brillo rojo y tipografía italizada
- **Campo de nombre de héroe** — placeholder `IDENTITY_REQUIRED`, ícono de identidad
- **Campo de contraseña** — placeholder `ENCRYPTION_KEY`, ícono de candado con toggle de visibilidad
- **Botón** `ACCESO AL CUARTEL ` con efecto de barrido al hover
- **Enlace** `¿NUEVO HÉROE? ÚNETE AL EQUIPO` para registro de nuevos agentes
- **Indicadores de estado** del protocolo S.H.I.E.L.D.:
  - Punto pulsante + `SECURE_LINK_ACTIVE`
  - Código de protocolo `S.H.I.E.L.D. PROTOCOL 084`
- **Footer** con copyright, `PRIVACY_PROTOCOL`, `TERMS_OF_ENGAGEMENT` y `CONTACT_HQ`

---

### Pantalla 2 — Trivia (`/quiz`)

Pantalla principal de juego. El agente demuestra su conocimiento del universo Marvel respondiendo preguntas por categoría.

#### Sidebar (panel lateral izquierdo)

| Sección | Descripción |
|---|---|
| Progreso de misión | Barra de avance visual con número de pregunta actual sobre el total |
| Puntuación acumulada | Contador de puntos en tiempo real |
| Categoría activa | Nombre e ícono de la categoría en curso |
| Perfil del agente | Nombre de héroe e imagen de avatar del usuario autenticado |

#### Tarjeta de pregunta (área principal)

- Etiqueta de categoría y número de pregunta (ej. `PREGUNTA 3 DE 10`)
- Texto de la pregunta destacado
- **Grid 2×2** con 4 opciones de respuesta:
  - Estado por defecto: borde neutro, fondo oscuro
  -  **Respuesta correcta:** resaltado en verde con ícono de confirmación
  -  **Respuesta incorrecta:** resaltado en rojo con ícono de error; se revela la opción correcta
- **Banner de resultado** (visible tras responder):
  - Indicador visual de acierto o fallo
  - Explicación breve de la respuesta correcta
- **Botón** `SIGUIENTE PREGUNTA →` para avanzar al siguiente ítem

---

## Diseño y Estética

### Paleta de colores

| Token | Hex | Uso |
|---|---|---|
| `--bg-dark` | `#0a0a0a` | Fondo principal |
| `--red` | `#ff2d2d` | Acento S.H.I.E.L.D., botones, bordes activos |
| `--text-dim` | `#888888` | Textos secundarios y placeholders |

### Tipografía

| Rol | Fuente | Características |
|---|---|---|
| Títulos | `Bebas Neue` | Itálica, bold, efecto glitch en hover |
| Interfaz y campos | `Share Tech Mono` | Monoespaciada, estilo terminal |
| Cuerpo | `Rajdhani` | Sans-serif técnica, legible |

### Efectos visuales

- Fondo de cómics en blanco y negro (Unsplash, libre de derechos)
- Overlay de scanlines y patrón halftone en rojo
- Barra de acento roja vertical izquierda
- Corte diagonal en esquina superior derecha de la tarjeta

---

## Modelo de Base de Datos (MongoDB)

Las preguntas se obtienen de una API externa y son enriquecidas con explicaciones generadas por IA (Claude). El modelo está diseñado para cachear ese contenido y evitar llamadas repetidas.

