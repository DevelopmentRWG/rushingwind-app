# Guia de Rol: UI Designer

> Sistema de diseno, componentes y pantallas de alta fidelidad para Rushing Wind App.

---

## Objetivo del Rol

Crear el sistema visual completo de ambas aplicaciones (usuario y operador) partiendo de la identidad existente en `pencil-new.pen`. Disenar las 28 pantallas necesarias con componentes reutilizables, manteniendo una estetica moderna orientada a Gen Z, con tema oscuro, gradientes rojo-purpura y tipografia Aeonik.

---

## Entregables Esperados

| Entregable | Formato | Descripcion |
|------------|---------|-------------|
| Design system completo | .pen file | Tokens, colores, tipografia, espaciado, componentes base documentados |
| Componentes reutilizables | .pen file | ~20 componentes catalogados con variantes y estados |
| Pantallas app usuario (18) | .pen file | Alta fidelidad, organizadas por modulo |
| Pantallas app operador (10) | .pen file | Alta fidelidad, formularios y dashboards |
| Prototipos de flujo | .pen file o herramienta de prototipado | Navegacion entre pantallas para los 9 flujos principales |

---

## Identidad Visual Existente

Estos son los tokens ya definidos en el archivo de diseno actual:

| Token | Valor | Uso |
|-------|-------|-----|
| Fondo principal | `#101010` | Background de todas las pantallas |
| Rojo primario | `#ff0030` | Acentos, botones, gradientes |
| Purpura primario | `#5830f1` | Acentos, tarjetas, gradientes |
| Tipografia | Aeonik | Toda la app |
| Esquinas redondeadas | 10-27px | Cards y botones (10 para cards, 27 para article cards, 62 para botones pill) |
| Texto principal | `#ffffff` | Titulos |
| Texto secundario | `#bfbfbf` | Subtitulos, metadata |
| Texto terciario | `#9e9e9e` | Detalles menores |

---

## Tareas por Fase

### Fase 1: Core (Prioridad Alta)

**Foco: Pulir existente + Biblia completa + Eventos usuario**

- **Design system base**: formalizar los tokens existentes en variables del .pen (colores, tipografia, espaciado, radios)
- **Pulir Home** (`app-home`):
  - Evaluar migracion de posicionamiento absoluto a auto-layout
  - Definir entry point para Devocional y Perfil
  - Disenar bottom navigation (4-5 tabs)
  - Corregir typos ("Knoledge" → "Knowledge", "hitorical" → "Historical")
- **Completar flujo Biblia**:
  - Disenar `app-bible-chapters` — grid de capitulos con estados (leido/no leido/en progreso)
  - Disenar `app-bible-reading` — vista de lectura de versiculos, navegacion entre capitulos
- **Disenar flujo completo de Eventos**:
  - Disenar componente `Event Card` con imagen, titulo, fecha, ubicacion, precio
  - Disenar `app-events` — listado con filtros
  - Disenar `app-event-detail` — detalle con hero image, info completa, tipos de boleto
  - Disenar `app-event-checkout` — seleccion de boleto, pago, confirmacion
- **Disenar Mis Boletos**:
  - Disenar componente `Ticket Card` con QR/codigo, estado
  - Disenar `app-my-tickets` — listado con filtro proximos/pasados

### Fase 2: Operador (Prioridad Alta)

**Foco: 10 pantallas de app operador desde cero**

- **Definir la identidad visual del operador**: misma base visual pero con matices que distingan la app (ej: acento de color diferente, layout mas denso para dashboards)
- **Disenar componentes de formulario**: Input Field, Text Area, Select/Dropdown, Toggle, Date/Time Picker — con estados (default, focused, filled, error, disabled)
- **Disenar componente Badge de Estado**: variantes para Borrador, Pendiente, Aprobado, Rechazado, Finalizado
- **Disenar pantallas**:
  - `op-login` — autenticacion del organizador
  - `op-dashboard` — resumen con metricas rapidas, eventos recientes, boton crear evento
  - `op-create-event` — formulario datos generales
  - `op-create-tickets` — configuracion de tipos de boleto
  - `op-event-preview` — preview y envio a aprobacion
  - `op-my-events` — listado con filtros por estado
  - `op-event-detail` — detalle con timeline de estado
- **Disenar Empty States**: para cuando no hay eventos creados, no hay boletos vendidos, etc.

### Fase 3: Contenido (Prioridad Media)

**Foco: Devocional, Articulos, Gamificacion, Perfil**

- **Disenar componente Devocional Card**: imagen, titulo, creador, tipo de contenido
- **Disenar pantallas de Devocional**:
  - `app-devocional` — categorias con hero card del dia
  - `app-devocional-detail` — contenido con info del creador, boton completar
- **Disenar detalle de articulo**:
  - `app-article-detail` — contenido largo, speaker info, articulos relacionados
- **Disenar sistema de gamificacion visual**:
  - `app-gamification` — puntos totales, racha, desglose por modulo, badges
  - Componente Progress Bar con variantes
  - Componente visual de racha (streak)
- **Disenar Perfil**:
  - `app-profile` — avatar, stats, accesos a boletos y configuracion

### Fase 4: Complementario (Prioridad Baja)

**Foco: Podcast, Growth Tracks, pantallas restantes operador**

- **Disenar componente Episode Card**: miniatura, titulo, invitado, duracion, boton play
- **Disenar componente Track Card**: nombre, dias, progreso, boton continuar/comenzar
- **Disenar pantallas de Guest/Podcast**:
  - `app-guest` — listado con episodio destacado
  - `app-guest-player` — reproductor completo
  - Componente Mini Player persistente
- **Disenar pantallas de Growth Tracks**:
  - `app-growth-tracks` — listado con progreso global
  - `app-growth-track-detail` — vista dia a dia con estados
- **Disenar pantallas restantes del operador**:
  - `op-ticket-management` — gestion de boletos vendidos, busqueda, check-in
  - `op-event-stats` — graficos de ventas, ingresos, conversion
  - `op-profile` — perfil de la organizacion, configuracion

---

## Dependencias

| Dependo de... | Para... |
|---------------|---------|
| **UX Researcher** | Personas, arquitectura de informacion validada, hallazgos de benchmarking |
| **Cliente (Rushing Wind)** | Assets de rebranding, nuevo arte, validacion de propuestas visuales |

| Dependen de mi... | Porque... |
|--------------------|-----------|
| **Frontend Developer** | Los disenos de alta fidelidad son el blueprint para la implementacion |
| **QA Tester** | Las pantallas definen el resultado visual esperado para los tests |
| **Backend Developer** | Los formularios y pantallas definen la estructura de datos necesaria |

---

## Referencias

| Documento | Relevancia |
|-----------|------------|
| `pencil-new.pen` | Diseno actual — punto de partida visual, 3 pantallas existentes |
| `estructura/pencil-new-structure.md` | Estructura detallada del .pen actual (IDs de nodos, componentes) |
| `estructura/componentes.md` | Catalogo de ~20 componentes (8 existentes + ~14 nuevos) |
| `estructura/pantallas-usuario.md` | 18 pantallas usuario con elementos principales por pantalla |
| `estructura/pantallas-operador.md` | 10 pantallas operador con elementos principales |
| `estructura/gap-analysis.md` | Comparacion existe vs falta, plan de fases |
| `estructura/requerimientos.md` | Estetica Gen Z, tema oscuro, gradientes, rebranding |
