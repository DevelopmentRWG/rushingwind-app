# Componentes Reutilizables

> Catalogo de componentes compartidos entre pantallas.
> Estado: "Existe" = ya definido en pencil-new.pen | "Nuevo" = por disenar

---

## Navegacion

### Top Bar / Menu
- **Estado**: Existe
- **Uso**: Todas las pantallas
- **Variantes**:
  - Home: logo centrado, avatar derecha (back y hamburguesa ocultos)
  - Interior: back visible a la izquierda, avatar derecha
- **Elementos**: bt-back, logo (Layer_1), menu-bt (hamburguesa), user-profile (avatar)

### Bottom Navigation
- **Estado**: Nuevo
- **Uso**: Pantallas principales (Home, Biblia, Eventos, Perfil)
- **Elementos**: 4-5 tabs con icono + label
- **Tabs sugeridos**: Home | Biblia | Eventos | Perfil (+ opcion de Devocional o mas)
- **Nota**: El diseno actual no tiene bottom nav; la navegacion es solo por tarjetas en home. Evaluar si se necesita para mejorar accesibilidad entre modulos.

### Tab Bar (horizontal)
- **Estado**: Existe
- **Uso**: Biblia (All Books / Chapter / Verses)
- **Elementos**: texto + linea activa debajo
- **Nota**: Reutilizable para otras secciones con tabs (ej: filtros de eventos)

---

## Tarjetas (Cards)

### Card Modulo Home
- **Estado**: Existe
- **Uso**: Home
- **Descripcion**: Tarjetas de acceso a modulos con fondo gradiente/color solido, texto de titulo y subtitulo
- **Variantes por tamano**: grande (390px ancho), mediano (~193px), pequeno (~140px)
- **Elementos**: rectangulo con gradiente/fill + texto titulo + texto subtitulo

### sec-book (Tarjeta de Libro)
- **Estado**: Existe
- **Uso**: Biblia - Listado de Libros
- **Elementos**:
  - Miniatura con gradiente (148x123, rounded 10)
  - Numero de libro (14px)
  - Nombre del libro (22px, #bfbfbf)
  - Progreso capitulos (12px, #bfbfbf)
  - Tiempo de lectura (10px, #9e9e9e)
  - Boton "Read now"

### Article Card
- **Estado**: Existe
- **Uso**: Articulos Biblicos
- **Elementos**:
  - Fondo purpura #5830f1 (rounded 27)
  - Avatar + nombre del speaker
  - Duracion (18px, #876af7)
  - Preview del contenido (18px, weight 500)
  - Boton "Read now"

### Event Card
- **Estado**: Nuevo
- **Uso**: Eventos - Listado (usuario), Mis Eventos (operador)
- **Elementos**:
  - Imagen del evento
  - Titulo del evento
  - Fecha y hora
  - Ubicacion
  - Organizador
  - Precio / "Gratis"
  - Badge de estado (solo en operador)

### Devocional Card
- **Estado**: Nuevo
- **Uso**: Devocional - Categorias y feed
- **Elementos**:
  - Imagen o icono de categoria
  - Titulo del devocional
  - Creador (avatar + nombre)
  - Duracion / tipo (texto, audio, video)

### Track Card
- **Estado**: Nuevo
- **Uso**: Growth Tracks - Listado
- **Elementos**:
  - Nombre del track
  - Duracion en dias
  - Barra de progreso
  - Tema/categoria
  - Boton "Continuar" / "Comenzar"

### Episode Card
- **Estado**: Nuevo
- **Uso**: Guest/Podcast - Listado
- **Elementos**:
  - Miniatura del episodio
  - Titulo
  - Nombre del invitado
  - Duracion
  - Boton play

### Ticket Card
- **Estado**: Nuevo
- **Uso**: Mis Boletos (usuario), Gestion Boletos (operador)
- **Elementos**:
  - Nombre del evento
  - Fecha
  - Tipo de boleto
  - Estado (proximo / pasado / valido / usado)
  - QR o codigo

---

## Botones

### bt-read-chapter (Boton "Read now")
- **Estado**: Existe
- **Uso**: Biblia, Articulos
- **Forma**: Pill (cornerRadius 62)
- **Variantes**:
  - Solo borde gradiente (rojo→purpura)
  - Fill gradiente (rojo→purpura o purpura→rojo)
  - Fill solido rojo (#ff0030)
- **Elementos**: texto "Read now" + icono flecha en circulo blanco

### Boton Primario
- **Estado**: Nuevo (derivar de bt-read-chapter)
- **Uso**: Global
- **Forma**: Pill
- **Variantes**: gradiente, rojo solido, purpura solido
- **Tamanos**: default (27px alto), grande (40-48px alto)

### Boton Secundario / Outline
- **Estado**: Nuevo
- **Uso**: Acciones secundarias
- **Forma**: Pill con solo borde
- **Variantes**: borde blanco, borde gradiente

### Boton Ghost / Text
- **Estado**: Nuevo
- **Uso**: Links, acciones terciarias
- **Solo texto**, sin fondo ni borde

---

## Avatares y Usuarios

### user-profile (Avatar)
- **Estado**: Existe
- **Uso**: Top bar, article cards, perfil
- **Tamano**: 40x40
- **Elementos**: circulo de fondo + silueta persona (head + body paths)
- **Variantes**:
  - Gris (#d9d9d9 fondo, #060620 silueta) - top bar
  - Negro (#000000 fondo, #dddddd silueta) - article cards
  - Con imagen (cuando el usuario suba foto)

### Speaker Info
- **Estado**: Existe (parcial dentro de article card)
- **Uso**: Articulos, Devocionales, Podcast
- **Elementos**: avatar + nombre del speaker + metadata (duracion, rol)

---

## Formularios (Nuevos)

### Input Field
- **Estado**: Nuevo
- **Uso**: Busqueda, formularios operador, login
- **Elementos**: placeholder text + linea inferior (estilo ya presente en busqueda de articulos)
- **Variantes**: default, focused, filled, error

### Text Area
- **Estado**: Nuevo
- **Uso**: Descripcion de evento
- **Elementos**: campo multilinia

### Select / Dropdown
- **Estado**: Nuevo
- **Uso**: Tipo de evento, filtros
- **Elementos**: campo con flecha, lista desplegable

### Toggle
- **Estado**: Nuevo
- **Uso**: Evento gratis si/no, configuraciones
- **Elementos**: switch on/off

### Date/Time Picker
- **Estado**: Nuevo
- **Uso**: Fecha de evento
- **Elementos**: campo con calendario

---

## Feedback y Estado

### Badge de Estado
- **Estado**: Nuevo
- **Uso**: Mis Eventos (operador)
- **Variantes**:
  - Borrador (gris)
  - Pendiente (amarillo)
  - Aprobado (verde)
  - Rechazado (rojo)
  - Finalizado (neutro)

### Progress Bar
- **Estado**: Nuevo
- **Uso**: Gamificacion, Growth Tracks, boleteria
- **Elementos**: barra horizontal con fill de progreso
- **Variantes**: gradiente, color solido

### Empty State
- **Estado**: Nuevo
- **Uso**: Listas vacias (sin eventos, sin boletos, etc.)
- **Elementos**: icono + mensaje + boton de accion

### Loading
- **Estado**: Nuevo
- **Uso**: Global
- **Elementos**: indicador de carga acorde al estilo visual

---

## Encabezados de Seccion

### Section Header
- **Estado**: Existe
- **Uso**: Biblia (encabezados de testamento)
- **Elementos**: texto de seccion (12px) + linea separadora blanca
- **Reutilizable para**: cualquier lista agrupada por categorias

---

## Reproductor de Audio (Nuevo)

### Mini Player
- **Uso**: Persistente al navegar mientras se reproduce un podcast/devocional
- **Elementos**: miniatura, titulo, boton play/pause, barra de progreso minima

### Player Completo
- **Uso**: Pantalla de reproduccion de Guest/Podcast
- **Elementos**: arte del episodio, titulo, speaker, controles completos, barra de progreso, velocidad
