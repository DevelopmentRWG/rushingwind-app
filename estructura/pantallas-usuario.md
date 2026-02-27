# Pantallas - App del Usuario

> Listado completo de pantallas necesarias para la aplicacion del usuario final.
> Estado: "Existe" = ya hay diseno en pencil-new.pen | "Nueva" = falta disenar

---

## Mapa de Navegacion

```
Onboarding → Home (hub central)
                ├── Biblia
                │   ├── Listado de Libros
                │   ├── Capitulos del Libro
                │   └── Lectura (versiculos)
                ├── Devocional
                │   ├── Categorias
                │   └── Detalle Devocional
                ├── Eventos
                │   ├── Listado de Eventos
                │   ├── Detalle del Evento
                │   └── Compra de Boleto
                ├── Guest / Podcast
                │   ├── Listado de Episodios
                │   └── Reproductor
                ├── Growth Tracks
                │   ├── Listado de Tracks
                │   └── Detalle Track (dia a dia)
                ├── Articulos Biblicos
                │   ├── Busqueda / Listado
                │   └── Detalle Articulo
                ├── Gamificacion
                │   └── Resumen (puntos, logros, racha)
                └── Perfil
                    ├── Mi Perfil
                    ├── Mis Boletos
                    └── Configuracion
```

---

## 1. Home

| Campo | Valor |
|-------|-------|
| Nombre | `app-home` |
| Estado | **Existe** (ID: `Gt57b`) |
| Acceso | Pantalla principal al abrir la app |

### Descripcion
Hub central con tarjetas de acceso rapido a cada modulo. Muestra estado de gamificacion (puntos), proximo evento, y accesos a Biblia, Devocional, Guest, Growth Tracks, Articulos y Eventos.

### Elementos principales
- Top bar con logo, avatar de usuario
- Tarjeta hero: Biblia (acceso directo a lectura)
- Tarjeta: Earning Points (resumen gamificacion)
- Tarjeta: Knowledge Tracks (progreso)
- Tarjeta: Bible Articles (acceso)
- Tarjeta: Guest (nuevos episodios)
- Tarjeta: Growth Tracks (dias)
- Tarjeta: Events (proximo evento con countdown)

### Notas
- Las tarjetas funcionan como entry points a cada modulo
- El layout usa posicionamiento libre (tipo bento grid)
- Cada tarjeta tiene gradiente y fondo caracteristico del modulo

---

## 2. Biblia - Listado de Libros

| Campo | Valor |
|-------|-------|
| Nombre | `app-bible-sec` |
| Estado | **Existe** (ID: `e5GK5`) |
| Acceso | Home → tarjeta "Bible" |

### Descripcion
Listado de todos los libros de la Biblia organizados por seccion (Antiguo Testamento, Nuevo Testamento) con tabs de navegacion.

### Elementos principales
- Top bar con boton back y avatar
- Tabs: All Books | Chapter | Verses
- Encabezado de seccion (ej: "Old testament: Book of the law")
- Tarjetas de libro (`sec-book`) con:
  - Miniatura con gradiente
  - Numero de libro, nombre, progreso de capitulos
  - Tiempo estimado de lectura
  - Boton "Read now"

### Notas
- Scroll vertical largo (1494px de alto)
- Progreso visual por libro (ej: "50/50 Chapters")
- Los tabs Chapter y Verses necesitan sus vistas correspondientes

---

## 3. Biblia - Capitulos del Libro

| Campo | Valor |
|-------|-------|
| Nombre | `app-bible-chapters` |
| Estado | **Nueva** |
| Acceso | Biblia Listado → tap en un libro |

### Descripcion
Grid o listado de capitulos del libro seleccionado. Muestra cuales estan leidos y cuales no.

### Elementos principales
- Top bar con back y nombre del libro
- Info del libro (nombre, total capitulos, progreso)
- Grid de capitulos numerados
- Estado visual: leido / no leido / en progreso
- Boton para continuar donde se quedo

---

## 4. Biblia - Lectura (Versiculos)

| Campo | Valor |
|-------|-------|
| Nombre | `app-bible-reading` |
| Estado | **Nueva** |
| Acceso | Capitulos → tap en un capitulo |

### Descripcion
Vista de lectura del capitulo seleccionado con versiculos numerados. Experiencia de lectura limpia y enfocada.

### Elementos principales
- Top bar minimalista con back, nombre del libro y capitulo
- Texto de versiculos numerados
- Navegacion entre capitulos (anterior / siguiente)
- Opcion de marcar como leido
- Fuente legible, espaciado generoso

---

## 5. Devocional - Categorias

| Campo | Valor |
|-------|-------|
| Nombre | `app-devocional` |
| Estado | **Nueva** |
| Acceso | Home → seccion devocional (por definir entry point) |

### Descripcion
Pantalla de seleccion de categoria de devocional. Cada categoria agrupa contenido tematico para diferentes segmentos.

### Elementos principales
- Top bar con back
- Titulo "Devocional"
- Tarjetas de categoria: Mujeres, Jovenes, Ninos, Matrimonio, General
- Devocional del dia destacado (hero card)
- Feed de devocionales recientes

---

## 6. Devocional - Detalle

| Campo | Valor |
|-------|-------|
| Nombre | `app-devocional-detail` |
| Estado | **Nueva** |
| Acceso | Devocional Categorias → tap en devocional |

### Descripcion
Contenido completo del devocional seleccionado. Puede incluir texto, audio o video segun el creador.

### Elementos principales
- Top bar con back
- Info del creador (avatar, nombre)
- Titulo del devocional
- Contenido (texto / reproductor de audio / video)
- Boton "Completar" (alimenta gamificacion)
- Devocionales relacionados

---

## 7. Eventos - Listado

| Campo | Valor |
|-------|-------|
| Nombre | `app-events` |
| Estado | **Nueva** |
| Acceso | Home → tarjeta "Events" |

### Descripcion
Feed de eventos disponibles publicados por iglesias y organizadores autorizados.

### Elementos principales
- Top bar con back y busqueda
- Filtros: fecha, ubicacion, tipo de evento
- Tarjetas de evento con:
  - Imagen/arte del evento
  - Titulo
  - Fecha y hora
  - Organizador
  - Ubicacion
  - Precio / "Gratis"
- Ordenados por fecha (proximos primero)

---

## 8. Eventos - Detalle

| Campo | Valor |
|-------|-------|
| Nombre | `app-event-detail` |
| Estado | **Nueva** |
| Acceso | Eventos Listado → tap en evento |

### Descripcion
Informacion completa del evento con opcion de compra de boleto.

### Elementos principales
- Imagen hero del evento (full width)
- Titulo del evento
- Fecha, hora, ubicacion con mapa
- Descripcion completa
- Info del organizador
- Tipos de boleto disponibles con precios
- Boton principal "Comprar Boleto" / "Reservar"
- Compartir evento

---

## 9. Eventos - Compra de Boleto

| Campo | Valor |
|-------|-------|
| Nombre | `app-event-checkout` |
| Estado | **Nueva** |
| Acceso | Evento Detalle → "Comprar Boleto" |

### Descripcion
Flujo de compra de boleto para un evento.

### Elementos principales
- Resumen del evento y tipo de boleto seleccionado
- Cantidad de boletos
- Metodo de pago
- Boton "Confirmar Compra"
- Pantalla de confirmacion / boleto generado

---

## 10. Guest / Podcast - Listado

| Campo | Valor |
|-------|-------|
| Nombre | `app-guest` |
| Estado | **Nueva** |
| Acceso | Home → tarjeta "Guest" |

### Descripcion
Listado de episodios de podcast / contenido de invitados.

### Elementos principales
- Top bar con back
- Episodio destacado (hero card)
- Listado de episodios con:
  - Miniatura
  - Titulo del episodio
  - Nombre del invitado
  - Duracion
  - Boton play

---

## 11. Guest / Podcast - Reproductor

| Campo | Valor |
|-------|-------|
| Nombre | `app-guest-player` |
| Estado | **Nueva** |
| Acceso | Guest Listado → tap en episodio |

### Descripcion
Reproductor de audio/video para el episodio seleccionado.

### Elementos principales
- Imagen/arte del episodio
- Titulo y nombre del invitado
- Controles de reproduccion (play/pause, avanzar, retroceder)
- Barra de progreso
- Velocidad de reproduccion
- Mini player persistente al navegar

---

## 12. Growth Tracks - Listado

| Campo | Valor |
|-------|-------|
| Nombre | `app-growth-tracks` |
| Estado | **Nueva** |
| Acceso | Home → tarjeta "Growth Tracks" o "Knowledge Tracks" |

### Descripcion
Listado de tracks de crecimiento espiritual disponibles con progreso.

### Elementos principales
- Top bar con back
- Resumen de progreso global (ej: "12/26 completed")
- Tarjetas de track con:
  - Nombre del track
  - Duracion en dias
  - Progreso (dias completados / total)
  - Tema/categoria
  - Boton "Continuar" o "Comenzar"

---

## 13. Growth Tracks - Detalle

| Campo | Valor |
|-------|-------|
| Nombre | `app-growth-track-detail` |
| Estado | **Nueva** |
| Acceso | Growth Tracks Listado → tap en track |

### Descripcion
Vista dia a dia del track seleccionado con contenido de cada dia.

### Elementos principales
- Top bar con back y nombre del track
- Barra de progreso visual
- Lista de dias con estado (completado / actual / bloqueado)
- Contenido del dia actual (texto, audio, actividad)
- Boton "Completar Dia"

---

## 14. Articulos Biblicos - Busqueda / Listado

| Campo | Valor |
|-------|-------|
| Nombre | `app-bible-articles` |
| Estado | **Existe** (ID: `vtCzT`) |
| Acceso | Home → tarjeta "Bible Articles" |

### Descripcion
Busqueda y listado de articulos biblicos con informacion de speakers.

### Elementos principales
- Top bar con back y avatar
- Titulo "The Bible explained"
- Barra de busqueda por tema
- Tarjetas de articulo con:
  - Fondo purpura
  - Avatar y nombre del speaker
  - Duracion
  - Preview del contenido
  - Boton "Read now"

### Notas
- Ya existe con 5 article cards
- Necesita pantalla de detalle del articulo

---

## 15. Articulos Biblicos - Detalle

| Campo | Valor |
|-------|-------|
| Nombre | `app-article-detail` |
| Estado | **Nueva** |
| Acceso | Articulos Listado → tap en articulo |

### Descripcion
Contenido completo del articulo biblico.

### Elementos principales
- Top bar con back
- Info del speaker (avatar, nombre, bio breve)
- Titulo del articulo
- Contenido completo (texto largo)
- Tiempo de lectura
- Articulos relacionados
- Boton "Completar" (gamificacion)

---

## 16. Gamificacion - Resumen

| Campo | Valor |
|-------|-------|
| Nombre | `app-gamification` |
| Estado | **Nueva** |
| Acceso | Home → tarjeta "Earning Points" o desde Perfil |

### Descripcion
Vista completa del progreso de gamificacion del usuario.

### Elementos principales
- Total de puntos acumulados
- Racha actual (dias consecutivos)
- Desglose de puntos por modulo
- Logros / badges obtenidos
- Historial de actividad reciente
- Metas pendientes

---

## 17. Perfil

| Campo | Valor |
|-------|-------|
| Nombre | `app-profile` |
| Estado | **Nueva** |
| Acceso | Home → avatar en top bar |

### Descripcion
Perfil del usuario con resumen de actividad y configuracion.

### Elementos principales
- Avatar y nombre del usuario
- Resumen de puntos y racha
- Estadisticas rapidas (libros leidos, eventos asistidos, tracks completados)
- Mis Boletos (acceso a boletos comprados)
- Configuracion (notificaciones, idioma, tema)
- Cerrar sesion

---

## 18. Mis Boletos

| Campo | Valor |
|-------|-------|
| Nombre | `app-my-tickets` |
| Estado | **Nueva** |
| Acceso | Perfil → "Mis Boletos" |

### Descripcion
Listado de boletos comprados por el usuario con estado.

### Elementos principales
- Listado de boletos con:
  - Evento asociado
  - Fecha del evento
  - Tipo de boleto
  - Estado (proximo / pasado)
  - QR o codigo del boleto
- Filtro: proximos / pasados

---

## Resumen de Pantallas

| # | Pantalla | Estado | Prioridad |
|---|----------|--------|-----------|
| 1 | Home | Existe | Alta |
| 2 | Biblia - Listado Libros | Existe | Alta |
| 3 | Biblia - Capitulos | Nueva | Alta |
| 4 | Biblia - Lectura | Nueva | Alta |
| 5 | Devocional - Categorias | Nueva | Media |
| 6 | Devocional - Detalle | Nueva | Media |
| 7 | Eventos - Listado | Nueva | Alta |
| 8 | Eventos - Detalle | Nueva | Alta |
| 9 | Eventos - Compra Boleto | Nueva | Alta |
| 10 | Guest - Listado | Nueva | Baja |
| 11 | Guest - Reproductor | Nueva | Baja |
| 12 | Growth Tracks - Listado | Nueva | Media-Baja |
| 13 | Growth Tracks - Detalle | Nueva | Media-Baja |
| 14 | Articulos - Listado | Existe | Media |
| 15 | Articulos - Detalle | Nueva | Media |
| 16 | Gamificacion - Resumen | Nueva | Media |
| 17 | Perfil | Nueva | Media |
| 18 | Mis Boletos | Nueva | Alta |

**Total: 18 pantallas** (3 existentes + 15 nuevas)
