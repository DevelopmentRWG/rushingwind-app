# Guia de Rol: Frontend Developer

> Implementacion de la interfaz de usuario, navegacion y consumo de APIs para ambas apps de Rushing Wind.

---

## Objetivo del Rol

Traducir los disenos de alta fidelidad en codigo funcional para las dos aplicaciones moviles (usuario y operador). Implementar la navegacion, componentes reutilizables, consumo de APIs y gestion de estado local, asegurando rendimiento y fidelidad visual al diseno.

---

## Entregables Esperados

| Entregable | Formato | Descripcion |
|------------|---------|-------------|
| Componentes UI reutilizables | Codigo | Libreria de ~20 componentes segun catalogo del diseno |
| Pantallas app usuario | Codigo | 18 pantallas implementadas con navegacion funcional |
| Pantallas app operador | Codigo | 10 pantallas implementadas con navegacion funcional |
| Integracion con APIs | Codigo | Consumo de todos los endpoints del backend |
| Gestion de estado | Codigo | Estado local y cache para datos frecuentes (progreso biblia, boletos, perfil) |
| Navegacion completa | Codigo | Stack de navegacion para ambas apps (tabs, stacks, modals) |

---

## Tareas por Fase

### Fase 1: Core (Prioridad Alta)

**Foco: Estructura base + Biblia + Eventos usuario**

- **Setup del proyecto**:
  - Configurar estructura de carpetas por modulo
  - Implementar tema global (colores, tipografia Aeonik, espaciado, radios)
  - Configurar navegacion base: bottom tabs (Home, Biblia, Eventos, Perfil) + stack navigation por modulo
- **Implementar componentes base**:
  - Top Bar (variantes: home con logo, interior con back)
  - Bottom Navigation (4-5 tabs con iconos)
  - Card Modulo Home (variantes por tamano: grande, mediano, pequeno)
  - sec-book card (miniatura, nombre, progreso, boton "Read now")
  - bt-read-chapter / Boton Primario (variantes: gradiente, solido, outline)
- **Implementar Home** (`app-home`):
  - Layout bento grid con tarjetas de modulos
  - Datos dinamicos: puntos de gamificacion, proximo evento, progreso biblia
  - Entry points funcionales a cada modulo
- **Implementar flujo Biblia**:
  - `app-bible-sec` — listado de libros con tabs, secciones AT/NT, scroll
  - `app-bible-chapters` — grid de capitulos con estados
  - `app-bible-reading` — vista de lectura con versiculos, navegacion entre capitulos, marcar como leido
  - Integracion con API de contenido biblico
  - Persistencia local de progreso de lectura
- **Implementar flujo Eventos usuario**:
  - Event Card component
  - `app-events` — listado con filtros (fecha, ubicacion, tipo)
  - `app-event-detail` — hero image, info, tipos de boleto
  - `app-event-checkout` — seleccion, pago, confirmacion
  - Integracion con API de eventos y pasarela de pago
- **Implementar Mis Boletos**:
  - Ticket Card component (con QR/codigo)
  - `app-my-tickets` — listado con filtro proximos/pasados

### Fase 2: Operador (Prioridad Alta)

**Foco: App operador completa**

- **Implementar componentes de formulario**:
  - Input Field (con estados: default, focused, filled, error, disabled)
  - Text Area
  - Select / Dropdown
  - Toggle
  - Date/Time Picker
  - Badge de Estado (Borrador, Pendiente, Aprobado, Rechazado, Finalizado)
- **Implementar navegacion operador**: estructura independiente (login → dashboard → tabs)
- **Implementar pantallas**:
  - `op-login` — autenticacion, gestion de sesion
  - `op-dashboard` — metricas rapidas, eventos recientes, acciones
  - `op-create-event` — formulario con validacion de campos
  - `op-create-tickets` — lista dinamica de tipos de boleto
  - `op-event-preview` — preview visual + envio a aprobacion
  - `op-my-events` — listado con filtros por estado
  - `op-event-detail` — timeline de estado, opciones de edicion
- **Implementar Empty States**: vistas cuando no hay datos (sin eventos, sin boletos)
- **Integracion con APIs**: CRUD de eventos, subida de imagenes, estados de aprobacion

### Fase 3: Contenido (Prioridad Media)

**Foco: Devocional, Articulos, Gamificacion, Perfil**

- **Implementar componentes nuevos**:
  - Devocional Card
  - Progress Bar (variantes: gradiente, solido)
  - Speaker Info (avatar + nombre + metadata)
- **Implementar Devocional**:
  - `app-devocional` — categorias con hero card
  - `app-devocional-detail` — contenido multimedia (texto/audio/video), boton completar
- **Implementar detalle de articulo**:
  - `app-article-detail` — contenido largo con scroll, speaker info, relacionados
- **Implementar Gamificacion**:
  - `app-gamification` — puntos, racha, desglose, badges
  - Logica de acumulacion de puntos por actividad
  - Visualizacion de racha (streak)
- **Implementar Perfil**:
  - `app-profile` — datos de usuario, stats, accesos
  - Configuracion (notificaciones, idioma, tema claro/oscuro)
  - Cerrar sesion

### Fase 4: Complementario (Prioridad Baja)

**Foco: Podcast, Growth Tracks, pantallas restantes operador**

- **Implementar componentes**:
  - Episode Card
  - Track Card
  - Mini Player (persistente entre pantallas)
  - Player Completo (controles, progreso, velocidad)
- **Implementar Guest/Podcast**:
  - `app-guest` — listado con episodio destacado
  - `app-guest-player` — reproductor con controles completos
  - Mini player global persistente en la navegacion
- **Implementar Growth Tracks**:
  - `app-growth-tracks` — listado con progreso global
  - `app-growth-track-detail` — dia a dia con estados, contenido por dia
- **Implementar pantallas restantes operador**:
  - `op-ticket-management` — lista de compradores, busqueda, exportar CSV, check-in QR
  - `op-event-stats` — graficos de ventas, ingresos, conversion
  - `op-profile` — datos de organizacion, configuracion

---

## Consideraciones Tecnicas

- **Tema dual**: el .pen tiene variables Light/Dark — implementar soporte para ambos temas con toggle en configuracion
- **Rendimiento**: listas largas (66 libros de la Biblia, listados de eventos) requieren virtualizacion
- **Offline**: considerar cache local para contenido biblico y boletos (el usuario necesita acceso al QR sin conexion)
- **Mini Player**: requiere estado global persistente que sobreviva la navegacion entre pantallas
- **Imagenes**: los eventos tienen arte/imagen subido por el operador — necesita optimizacion y carga progresiva
- **Deep linking**: los eventos pueden compartirse — necesitan URLs profundas

---

## Dependencias

| Dependo de... | Para... |
|---------------|---------|
| **UI Designer** | Disenos de alta fidelidad, design tokens, especificaciones de componentes |
| **Backend Developer** | APIs documentadas, endpoints funcionales, esquema de datos |
| **UX Researcher** | Estructura de navegacion validada, flujos refinados |

| Dependen de mi... | Porque... |
|--------------------|-----------|
| **QA Tester** | La implementacion es lo que se testea — necesita builds funcionales |
| **UI Designer** | Feedback sobre viabilidad tecnica de las propuestas de diseno |

---

## Referencias

| Documento | Relevancia |
|-----------|------------|
| `estructura/componentes.md` | Catalogo de ~20 componentes con especificaciones |
| `estructura/pantallas-usuario.md` | 18 pantallas con elementos principales |
| `estructura/pantallas-operador.md` | 10 pantallas con elementos principales |
| `estructura/flujos.md` | 9 flujos con pantallas involucradas y puntos clave |
| `estructura/modulos.md` | Relaciones entre modulos — informa la estructura de navegacion |
| `pencil-new.pen` | Archivo de diseno — fuente de verdad visual |
| `estructura/pencil-new-structure.md` | Estructura del .pen (IDs, nodos, tokens) |
