# Guia de Rol: UX Researcher

> Investigacion, arquitectura de informacion y validacion de flujos para Rushing Wind App.

---

## Objetivo del Rol

Asegurar que cada decision de diseno e implementacion este respaldada por un entendimiento solido del usuario final (Gen Z cristiana), del contexto cultural (Norteamerica y Latinoamerica), y de las mejores practicas en apps de contenido y boleteria. El UX Researcher proporciona la base sobre la cual el equipo construye.

---

## Entregables Esperados

| Entregable | Formato | Descripcion |
|------------|---------|-------------|
| Personas de usuario | Documento | 3-4 arquetipos: usuario casual, usuario comprometido, creador de contenido, operador/iglesia |
| Mapa de arquitectura de informacion | Diagrama | Jerarquia de navegacion completa (ambas apps) validada contra los flujos existentes |
| Benchmarking competitivo | Documento | Analisis de 4-6 apps comparables (Bible App, Eventbrite, Spotify, Subsplash, Church Center) |
| Validacion de flujos criticos | Reporte | Revision de los 9 flujos documentados con observaciones y mejoras |
| Lineamientos de contenido | Documento | Tono de voz, terminologia, consideraciones culturales para la audiencia objetivo |

---

## Tareas por Fase

### Fase 1: Core (Prioridad Alta)

**Foco: Biblia + Eventos usuario + Home**

- Definir personas primarias: usuario Gen Z que lee la Biblia, usuario que busca eventos
- Validar la arquitectura de navegacion del Home como hub central — evaluar si las tarjetas bento son suficientes o se necesita bottom navigation
- Revisar flujo de lectura de la Biblia (Flujo 1): analizar si la jerarquia Libros → Capitulos → Versiculos es intuitiva para el publico objetivo
- Revisar flujo de compra de boletos (Flujo 2): mapear puntos de friccion potenciales en el checkout
- Benchmarking de apps de Biblia: YouVersion, Bible App, Glorify — patrones de lectura, progreso, gamificacion
- Benchmarking de apps de boleteria: Eventbrite, Dice, Ticketmaster — patrones de descubrimiento y compra de boletos
- Definir criterios de exito para "Mis Boletos" — que informacion necesita el usuario antes, durante y despues del evento

### Fase 2: Operador (Prioridad Alta)

**Foco: App completa del operador**

- Definir persona del operador: iglesia/organizador que crea eventos, necesidades y frustraciones
- Validar el flujo de creacion de evento (Flujo 8): revisar si el wizard de 3 pasos (datos → boleteria → preview) es el patron correcto
- Investigar el proceso de aprobacion: como comunicar estados al operador de forma clara (pendiente, aprobado, rechazado)
- Benchmarking de herramientas de organizador: Eventbrite organizer, Meetup organizer — mejores practicas para dashboards y gestion
- Validar flujo de gestion post-publicacion (Flujo 9): check-in, estadisticas, gestion de boletos vendidos
- Evaluar si el operador necesita acceso desde mobile o si desktop es suficiente para ciertas tareas

### Fase 3: Contenido (Prioridad Media)

**Foco: Devocional, Articulos, Gamificacion, Perfil**

- Validar la segmentacion de devocionales por tema (Mujeres, Jovenes, etc.) — confirmar que los segmentos son relevantes para la audiencia
- Revisar flujo de consumo de devocional (Flujo 3): evaluar si la experiencia de "completar" un devocional es clara
- Investigar patrones de gamificacion en apps de habitos: Duolingo, Headspace, Strava — que mecanicas funcionan mejor para retencion
- Definir que metricas de gamificacion son visibles en el perfil vs en el home
- Revisar flujo de articulos biblicos (Flujo 6): evaluar la experiencia de busqueda por tema

### Fase 4: Complementario (Prioridad Baja)

**Foco: Podcast, Growth Tracks, gestion boletos operador, estadisticas**

- Validar flujo de podcast/Guest (Flujo 4): evaluar si el mini player persistente es viable y necesario
- Revisar flujo de Growth Tracks (Flujo 5): investigar patrones de contenido dia-a-dia (ej: Headspace cursos, Duolingo unidades)
- Evaluar estadisticas del operador: que datos realmente necesita un organizador de evento
- Revision final de toda la arquitectura de informacion con todos los modulos integrados

---

## Dependencias

| Dependo de... | Para... |
|---------------|---------|
| **Cliente (Rushing Wind)** | Clarificar dudas sobre la audiencia, validar personas, acceso a datos de usuarios existentes |
| **UI Designer** | Alinear hallazgos de research con decisiones de diseno visual |
| **Backend Developer** | Entender limitaciones tecnicas que afecten la arquitectura de informacion |

| Dependen de mi... | Porque... |
|--------------------|-----------|
| **UI Designer** | Las personas y la arquitectura de informacion guian el diseno de pantallas |
| **Frontend Developer** | La validacion de flujos define la navegacion a implementar |
| **QA Tester** | Los criterios de exito de cada flujo son la base de los tests de aceptacion |

---

## Referencias

| Documento | Relevancia |
|-----------|------------|
| `estructura/requerimientos.md` | Contexto del producto, publico objetivo, restricciones |
| `estructura/modulos.md` | 7 modulos y sus relaciones — base para la arquitectura de informacion |
| `estructura/flujos.md` | 9 flujos a validar y refinar |
| `estructura/pantallas-usuario.md` | 18 pantallas usuario — mapa de navegacion actual |
| `estructura/pantallas-operador.md` | 10 pantallas operador — mapa de navegacion actual |
| `estructura/gap-analysis.md` | Estado actual vs deseado, plan de fases |
