# Modulos - Rushing Wind App

> Cada modulo funciona como un "hobby" donde el usuario habita y consume contenido.

---

## Mapa General

```
┌─────────────────────────────────────────────────────────┐
│                    RUSHING WIND APP                       │
├─────────────────────────────────────────────────────────┤
│                                                          │
│  ┌──────────┐  ┌──────────┐  ┌──────────────────────┐  │
│  │  BIBLIA  │  │DEVOCIONAL│  │  EVENTOS / BOLETERIA │  │
│  │ (core)   │  │ (premium)│  │    (diferenciador)   │  │
│  └────┬─────┘  └────┬─────┘  └──────────┬───────────┘  │
│       │              │                   │               │
│  ┌────┴─────┐  ┌────┴─────┐  ┌──────────┴───────────┐  │
│  │ARTICULOS │  │  GROWTH  │  │   GUEST / PODCAST    │  │
│  │ BIBLICOS │  │  TRACKS  │  │                      │  │
│  └──────────┘  └──────────┘  └──────────────────────┘  │
│                                                          │
│  ┌──────────────────────────────────────────────────┐   │
│  │              GAMIFICACION (transversal)            │   │
│  │         Puntos · Rachas · Progreso · Logros       │   │
│  └──────────────────────────────────────────────────┘   │
│                                                          │
└─────────────────────────────────────────────────────────┘
```

---

## 1. Biblia (Modulo Principal)

**Proposito**: Lectura completa de la Biblia con progreso y experiencia moderna.

### Funcionalidades
- Navegacion: Testamento → Libro → Capitulo → Versiculo
- 66 libros organizados por secciones (Ley, Historicos, Poeticos, Profeticos, Evangelios, Cartas, etc.)
- Progreso por libro (ej: "50/50 capitulos")
- Tiempo estimado de lectura por libro
- Marcado de capitulos leidos
- Boton "Read now" para continuar donde se quedo

### Relacion con otros modulos
- Alimenta **Gamificacion** (puntos por capitulos leidos)
- Conecta con **Articulos Biblicos** (explicaciones de lo que se lee)
- Base para contenido de **Devocional**

### Estado actual en el diseno
- Pantalla `app-bible-sec` con listado de libros, tabs (All Books / Chapter / Verses)
- Tarjeta "Bible" en home con acceso directo
- Estructura de `sec-book` cards ya definida

---

## 2. Devocional (Premium)

**Proposito**: Contenido devocional segmentado por temas para conexion personal con Dios.

### Funcionalidades
- Feed de devocionales organizados por tema
- Categorias: Mujeres, Jovenes, Ninos, Bebes, Matrimonio, General
- Creadores/predicadores como autores del contenido
- Devocional diario o por serie
- Contenido multimedia (texto, audio, video)

### Relacion con otros modulos
- Alimenta **Gamificacion** (puntos por devocional completado)
- Comparte creadores con **Articulos Biblicos** y **Guest/Podcast**
- Conecta tematicamente con **Growth Tracks**

### Estado actual en el diseno
- No tiene pantalla dedicada
- Concepto parcialmente cubierto por `app-bible-articles`
- Necesita pantalla propia con navegacion por temas

---

## 3. Eventos / Boleteria (Diferenciador)

**Proposito**: Plataforma donde iglesias y organizadores publican eventos y venden boletos.

### Funcionalidades - Lado Usuario
- Feed de eventos disponibles
- Filtrado por fecha, ubicacion, tipo
- Detalle del evento (titulo, fecha, descripcion, lugar, organizador)
- Compra de boletos
- Mis boletos / eventos guardados
- Countdown al evento ("In 3 days")

### Funcionalidades - Lado Operador
- Crear evento (formulario completo)
- Subir imagen/arte del evento
- Configurar boleteria (tipos de boleto, precio, cantidad)
- Enviar a autorizacion de Rushing Wind
- Ver estado de aprobacion
- Gestionar asistentes
- Estadisticas del evento

### Relacion con otros modulos
- Alimenta **Gamificacion** (puntos por asistencia)
- Visibilidad desde **Home** (tarjeta de proximo evento)
- Independiente de los modulos de contenido biblico

### Estado actual en el diseno
- Solo tarjeta "Events" en home con "Next Event Title" e "In 3 days"
- No existe pantalla de listado de eventos
- No existe pantalla de detalle de evento
- No existe flujo de compra de boletos
- No existe app del operador

---

## 4. Guest / Podcast

**Proposito**: Contenido de invitados en formato episodio (audio/video).

### Funcionalidades
- Listado de episodios
- Reproductor de audio/video
- Info del invitado (nombre, foto, bio)
- Nuevos episodios destacados
- Historial de reproduccion

### Relacion con otros modulos
- Comparte creadores con **Devocional** y **Articulos**
- Alimenta **Gamificacion** (puntos por escuchar)
- Acceso desde **Home** (tarjeta "Guest")

### Estado actual en el diseno
- Tarjeta "Guest / 13 new episodes" en home
- No existe pantalla de listado ni reproductor

---

## 5. Growth Tracks

**Proposito**: Caminos de crecimiento espiritual estructurados por dias.

### Funcionalidades
- Listado de tracks disponibles
- Progreso por track (ej: "12/26 completed")
- Contenido diario dentro de cada track
- Conteo de dias consecutivos
- Tracks variados por tema y duracion

### Relacion con otros modulos
- Fuertemente ligado a **Gamificacion** (rachas, puntos)
- Complementario a **Devocional** (enfoque mas estructurado)
- Acceso desde **Home** (tarjeta "Knowledge Tracks")

### Estado actual en el diseno
- Tarjeta "Knowledge Tracks / 12/26 completed" en home
- Tarjeta "Growth Tracks / 5 days" en home
- No existe pantalla de listado ni detalle de track

---

## 6. Articulos Biblicos

**Proposito**: Enciclopedia biblica con articulos explicativos de speakers/autores.

### Funcionalidades
- Busqueda por tema/subject
- Feed de articulos con preview
- Detalle del articulo completo
- Info del speaker (avatar, nombre)
- Duracion estimada de lectura
- Articulos relacionados

### Relacion con otros modulos
- Complementa la lectura de **Biblia**
- Comparte creadores con **Devocional** y **Guest**
- Alimenta **Gamificacion** (puntos por articulo leido)

### Estado actual en el diseno
- Pantalla `app-bible-articles` con busqueda y 5 article cards
- Estructura basica funcional, necesita pulir

---

## 7. Gamificacion (Transversal)

**Proposito**: Sistema de recompensas que incentiva el uso constante de todos los modulos.

### Funcionalidades
- **Puntos** acumulables por actividad (lectura, devocional, asistencia, etc.)
- **Rachas** de dias consecutivos de uso
- **Progreso** visible por modulo
- **Logros** / badges por metas alcanzadas
- Resumen en home visible siempre

### Relacion con otros modulos
- **Transversal**: todos los modulos alimentan el sistema de puntos
- Visible en **Home** y en **Perfil**
- Motor principal de retencion y engagement

### Estado actual en el diseno
- Tarjeta "1350 Earning Points" en home
- Progreso en bible-sec (capitulos leidos)
- No existe pantalla dedicada de logros/progreso global

---

## Resumen de Prioridades por Modulo

| Modulo | Prioridad | Razon |
|--------|-----------|-------|
| Biblia | Alta | Modulo principal, ya existe parcialmente |
| Eventos/Boleteria | Alta | Diferenciador clave, falta casi todo |
| Devocional | Media | Core de engagement, no tiene pantalla propia |
| Gamificacion | Media | Transversal, existe parcial en home |
| Growth Tracks | Media-Baja | Complementario, solo tarjetas en home |
| Articulos Biblicos | Media-Baja | Existe basico, necesita pulir |
| Guest/Podcast | Baja | Solo tarjeta en home |
