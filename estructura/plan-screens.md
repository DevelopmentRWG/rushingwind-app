# Plan de Diseno de Pantallas - Rushing Wind App

> Plan completo para disenar todas las pantallas faltantes en `rushingwind-new-structure.pen`

---

## Estado Actual (Lo que ya existe — 73 frames)

| Categoria | Pantallas | IDs |
|-----------|-----------|-----|
| **Home** | app-home | `Gt57b` |
| **Biblia** | Listado de libros, Capitulos (2 variantes oscuro/claro), Lectura/versiculos, Seleccion de capitulo, Puntos por capitulo | `e5GK5`, `JM6oD`, `d1uCh`, `CKACh`, `WeW7z`, `FQynL`, `Fcbdm` |
| **Articulos Biblicos** | Lista de articulos, Seleccion de speaker (2 variantes), Vista completa de articulo | `vtCzT`, `AcvTi`, `j4Vlw`, `oClZD` |
| **Growth Tracks** | Lista de growth (3 variantes), Viaje/itinerario (4 variantes), Detalle de itinerario, Dia de itinerario, Seleccion de growth (3 variantes) | `Elh21`, `9BEFI`, `fNWFD`, `pX1HN`, `GSWEU`, `Y8FcD`, `Vd5zk`, `DooMo`, `OKBRt`, `Fiued`, `y36YK`, `ljch6` |
| **Assets/Componentes** | Barras de menu, botones, tarjetas de libro, secciones de capitulo, posts de speaker, botones de pago, botones de like, etc. | ~30 frames pequenos en area negativa-x |
| **Gamificacion** | Tabla de posiciones / puntos | `Fcbdm` |

---

## Lo que Falta (Pantallas a Crear)

### Fase 1: Flujo de Eventos (Usuario) — 5 pantallas, PRIORIDAD MAXIMA

| # | Nombre | Descripcion |
|---|--------|-------------|
| 1 | `app-events` | Listado de eventos con filtros y Event Cards |
| 2 | `app-event-detail` | Detalle del evento con imagen hero, info completa, tipos de boleto |
| 3 | `app-event-checkout` | Flujo de compra de boleto (seleccion de tipo, pago, confirmacion) |
| 4 | `app-my-tickets` | Lista de boletos comprados del usuario |
| 5 | `app-event-confirmation` | Confirmacion post-compra con codigo QR |

### Fase 2: App del Operador — 10 pantallas

| # | Nombre | Descripcion |
|---|--------|-------------|
| 6 | `op-login` | Autenticacion del operador |
| 7 | `op-dashboard` | Resumen con metricas, eventos recientes, boton crear |
| 8 | `op-create-event` | Formulario: titulo, descripcion, imagen, fecha, ubicacion |
| 9 | `op-create-tickets` | Configuracion de tipos de boleto |
| 10 | `op-event-preview` | Preview + enviar a aprobacion |
| 11 | `op-my-events` | Lista de eventos con badges de estado |
| 12 | `op-event-detail` | Detalle del evento con timeline de estado |
| 13 | `op-ticket-management` | Boletos vendidos, busqueda, check-in |
| 14 | `op-event-stats` | Graficos de ventas, metricas |
| 15 | `op-profile` | Perfil de la organizacion |

### Fase 3: Contenido — 4 pantallas

| # | Nombre | Descripcion |
|---|--------|-------------|
| 16 | `app-devocional` | Categorias de devocional con hero card del dia |
| 17 | `app-devocional-detail` | Contenido del devocional (texto/audio/video) |
| 18 | `app-profile` | Perfil del usuario con estadisticas |
| 19 | `app-gamification` | Resumen completo de gamificacion (puntos, racha, badges) |

### Fase 4: Complementario — 3 pantallas

| # | Nombre | Descripcion |
|---|--------|-------------|
| 20 | `app-guest` | Listado de episodios de podcast/Guest |
| 21 | `app-guest-player` | Reproductor completo de audio/video |
| 22 | `app-settings` | Configuracion de la app (notificaciones, idioma, tema) |

---

## Tokens de Diseno (Hardcoded, extraidos de pantallas existentes)

| Token | Valor | Uso |
|-------|-------|-----|
| Fondo principal | `#101010` | Background de todas las pantallas |
| Superficie de tarjeta | `#212121` | Cards, secciones elevadas |
| Superficie secundaria | `#282828` | Comentarios, inputs |
| Rojo primario | `#ff0030` | Acentos, botones, gradientes |
| Purpura primario | `#5830f1` | Acentos, tarjetas, gradientes |
| Purpura variante | `#7921f5` | Gradientes alternos |
| Purpura claro | `#8a38f5` | Bordes de componentes, acentos suaves |
| Rosa | `#df7bcf` | Acentos terciarios |
| Texto primario | `#ffffff` | Titulos, texto principal |
| Texto secundario | `#bfbfbf` | Subtitulos, metadata |
| Texto terciario | `#9e9e9e` | Detalles menores |
| Texto cuaternario | `#c2c2c2` | Descripciones |
| Tipografia | Aeonik | Toda la app |
| Radio tarjetas home | 25px | Tarjetas del home |
| Radio tarjetas libro | 10px | sec-book cards |
| Radio secciones | 13px | chapter-sec, speaker-episodes |
| Radio botones pill | 62px | bt-read-chapter, CTAs principales |
| Radio speaker post | 17px | Tarjetas de speaker |
| Ancho de pantalla | 440px | Todas las pantallas |
| Gradiente principal | `#ff0030` → `#7921f5` | Botones, fondos hero, acentos |

### Pesos Tipograficos Usados

| Peso | Uso |
|------|-----|
| 300 (Light) | Titulos grandes (35-45px), numeros destacados |
| 400 (Normal) | Texto de cuerpo, subtitulos (16px) |
| 500 (Medium) | Nombres de libros (22px), labels de botones |
| 700 (Bold) | Labels de descripcion, titulos de seccion |

### Tamanos Tipograficos

| Tamano | Uso |
|--------|-----|
| 45px | Titulos hero (ej: "Bible") |
| 35px | Titulos de seccion (ej: "Events", "Guest", numeros grandes) |
| 22px | Nombres (ej: tabs, nombres de libros) |
| 18px | Subtitulos (ej: "66 chapters") |
| 16px | Texto de cuerpo, labels de modulo |
| 14px | Labels pequenos (ej: "Book 1") |
| 12px | Metadata (ej: "50/50 Chapters", "Read now", secciones AT/NT) |
| 10px | Texto minimo (ej: "6h50m reading") |

---

## Estrategia de Ejecucion

### Componentes Reutilizables Primero

Antes de construir pantallas, crear componentes reutilizables y colocarlos en el area de assets (x negativa):

1. **Bottom Navigation** — 4-5 tabs con icono + label
2. **Event Card** — Imagen, titulo, fecha, ubicacion, precio
3. **Ticket Card** — Evento, fecha, tipo, estado, QR
4. **Devocional Card** — Imagen, titulo, creador, tipo
5. **Input Field** — Con estados (default, focused, error)
6. **Text Area** — Campo multilinia
7. **Toggle** — Switch on/off
8. **Status Badge** — Variantes: Borrador, Pendiente, Aprobado, Rechazado, Finalizado
9. **Progress Bar** — Con gradiente y solido

### Patrones a Copiar

| Patron existente | Copiar para... |
|------------------|----------------|
| Menu bar (`S8si2` / `kSXaq`) | Todas las pantallas nuevas |
| sec-book card (`x8kF3`) | Base para Event Card, Devocional Card |
| chapter-sec (`Sz1D0`) | Base para ticket rows, form rows |
| speaker-post (`l0NxW`) | Base para Event Card con imagen |
| bt-read-chapter (`T6uXi`) | CTAs primarios en nuevas pantallas |
| bt-payment (`ZDGsS`) | Boton de compra en checkout |
| comment-user (`XJP1Y`) | Rows de lista en operador |

### Layout Consistente por Pantalla

```
┌─────────────────────────────┐
│ Status Bar (62px)           │  ← Opcional, respetando safe area
├─────────────────────────────┤
│ Menu / Top Bar (65px)       │  ← Copiar de existente
├─────────────────────────────┤
│                             │
│ Contenido Principal         │  ← Vertical scroll
│ (padding: 25px horizontal)  │
│                             │
├─────────────────────────────┤
│ Bottom Navigation (62px)    │  ← Nuevo componente (pantallas principales)
└─────────────────────────────┘
```

### Reglas de Operacion

- Maximo 25 operaciones por llamada `batch_design`
- Dividir pantallas en secciones logicas (estructura → contenido → detalles)
- Verificar con screenshot despues de cada pantalla principal
- Colocar pantallas nuevas a la derecha del contenido existente (x > 3800)
- Usar `placeholder: true` durante la construccion, remover al terminar

### Posicionamiento de Pantallas Nuevas

```
Fila 1 (y: 0):       Eventos usuario (5 pantallas)
  x: 4000             app-events
  x: 4500             app-event-detail
  x: 5000             app-event-checkout
  x: 5500             app-my-tickets
  x: 6000             app-event-confirmation

Fila 2 (y: 1500):    Operador (10 pantallas)
  x: 4000             op-login
  x: 4500             op-dashboard
  x: 5000             op-create-event
  x: 5500             op-create-tickets
  x: 6000             op-event-preview
  x: 6500             op-my-events
  x: 7000             op-event-detail
  x: 7500             op-ticket-management
  x: 8000             op-event-stats
  x: 8500             op-profile

Fila 3 (y: 3200):    Contenido (4 pantallas)
  x: 4000             app-devocional
  x: 4500             app-devocional-detail
  x: 5000             app-profile
  x: 5500             app-gamification

Fila 4 (y: 4700):    Complementario (3 pantallas)
  x: 4000             app-guest
  x: 4500             app-guest-player
  x: 5000             app-settings
```

---

## Estimacion de Esfuerzo

| Fase | Pantallas | Llamadas batch_design estimadas | Prioridad |
|------|-----------|--------------------------------|-----------|
| Componentes reutilizables | 9 componentes | 5-8 | Alta |
| Fase 1: Eventos usuario | 5 pantallas | 12-15 | Alta |
| Fase 2: Operador | 10 pantallas | 20-25 | Alta |
| Fase 3: Contenido | 4 pantallas | 8-10 | Media |
| Fase 4: Complementario | 3 pantallas | 6-8 | Baja |
| **Total** | **22 pantallas + 9 componentes** | **~50-66 llamadas** | — |

---

## Metricas de Completitud Proyectada

```
Estado actual (73 frames):   ████████████░░░░░░░░  ~55%
Post Fase 1 (Eventos):       █████████████████░░░  ~70%
Post Fase 2 (Operador):      ██████████████████░░  ~85%
Post Fase 3 (Contenido):     ███████████████████░  ~93%
Post Fase 4 (Complementario):████████████████████  100%
```

> Nota: El porcentaje sube significativamente respecto al gap-analysis original porque el archivo `rushingwind-new-structure.pen` ya contiene muchas mas pantallas de las que habiamos documentado inicialmente en `pencil-new.pen`.

---

## Referencias

| Documento | Relevancia |
|-----------|------------|
| `estructura/pantallas-usuario.md` | Especificaciones de 18 pantallas usuario |
| `estructura/pantallas-operador.md` | Especificaciones de 10 pantallas operador |
| `estructura/componentes.md` | Catalogo de componentes existentes y nuevos |
| `estructura/flujos.md` | 9 flujos principales — contexto de navegacion |
| `estructura/gap-analysis.md` | Plan de 4 fases original |
| `estructura/ux/ui-designer.md` | Guia del UI Designer con tokens y tareas |
| `rushingwind-new-structure.pen` | Archivo de diseno — fuente de verdad |
