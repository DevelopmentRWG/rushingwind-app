# Gap Analysis - Diseno Actual vs Requerimientos

> Comparacion entre lo que existe en pencil-new.pen y lo que se necesita segun los recordings.

---

## Resumen Ejecutivo

| Categoria | Existe | Falta | Total |
|-----------|--------|-------|-------|
| Pantallas usuario | 3 | 15 | 18 |
| Pantallas operador | 0 | 10 | 10 |
| Componentes | 6 | 14 | ~20 |
| Flujos completos | 0 | 9 | 9 |

**El diseno actual cubre ~10% del producto final.** Las 3 pantallas existentes (Home, Biblia Libros, Articulos) son un buen punto de partida para identidad visual y patrones de componentes, pero falta la gran mayoria de funcionalidad.

---

## Por Modulo

### Biblia
| Elemento | Estado | Referencia .pen | Notas |
|----------|--------|-----------------|-------|
| Tarjeta en Home | Existe | `na6WR` (bible-sec) | Funcional |
| Listado de libros | Existe | `e5GK5` (app-bible-sec) | Funcional, necesita pulir |
| Tabs (Books/Chapter/Verses) | Existe | `A1Vyp` (Frame 12) | Solo la estructura, faltan vistas de Chapter y Verses |
| sec-book card | Existe | `x8kF3` y variantes | Patron definido, reutilizable |
| Encabezados de seccion (AT/NT) | Existe | `J5Q4R`, `BTSgj` | Funcional |
| Pantalla de capitulos | **Falta** | - | Nueva pantalla necesaria |
| Pantalla de lectura/versiculos | **Falta** | - | Nueva pantalla necesaria |
| Progreso de lectura | Parcial | Texto "50/50 Chapters" | Existe como texto, falta logica visual |

### Eventos / Boleteria
| Elemento | Estado | Referencia .pen | Notas |
|----------|--------|-----------------|-------|
| Tarjeta en Home | Existe | `f3aSf` (event-sec) | Solo muestra "Events" + "In 3 days" |
| Listado de eventos | **Falta** | - | Pantalla critica, nueva |
| Detalle de evento | **Falta** | - | Pantalla critica, nueva |
| Compra de boleto | **Falta** | - | Pantalla critica, nueva |
| Event card (componente) | **Falta** | - | Nuevo componente |
| Ticket card (componente) | **Falta** | - | Nuevo componente |
| Mis Boletos | **Falta** | - | Pantalla nueva |
| App operador completa | **Falta** | - | 10 pantallas nuevas |

### Devocional
| Elemento | Estado | Referencia .pen | Notas |
|----------|--------|-----------------|-------|
| Pantalla de categorias | **Falta** | - | Nueva pantalla |
| Detalle de devocional | **Falta** | - | Nueva pantalla |
| Devocional card (componente) | **Falta** | - | Nuevo componente |
| Navegacion por temas | **Falta** | - | Jovenes, mujeres, matrimonio, etc. |

### Guest / Podcast
| Elemento | Estado | Referencia .pen | Notas |
|----------|--------|-----------------|-------|
| Tarjeta en Home | Existe | `FgP1n` (guest-sec) | "Guest / 13 new episodes" |
| Listado de episodios | **Falta** | - | Nueva pantalla |
| Reproductor | **Falta** | - | Nueva pantalla |
| Mini player | **Falta** | - | Nuevo componente |
| Episode card (componente) | **Falta** | - | Nuevo componente |

### Growth Tracks
| Elemento | Estado | Referencia .pen | Notas |
|----------|--------|-----------------|-------|
| Tarjeta en Home (Knowledge) | Existe | `7EjSU` (days-sec) | "12/26 completed" |
| Tarjeta en Home (Growth) | Existe | `VOgYs` (growth-sec) | "5 days" |
| Listado de tracks | **Falta** | - | Nueva pantalla |
| Detalle de track | **Falta** | - | Nueva pantalla |
| Track card (componente) | **Falta** | - | Nuevo componente |
| Progress bar (componente) | **Falta** | - | Nuevo componente |

### Articulos Biblicos
| Elemento | Estado | Referencia .pen | Notas |
|----------|--------|-----------------|-------|
| Tarjeta en Home | Existe | `fjbK0` (bible-sec) | "Bible Articles" |
| Listado con busqueda | Existe | `vtCzT` (app-bible-articles) | Funcional |
| Article card | Existe | `xrJw5` y variantes | Patron definido |
| Barra de busqueda | Existe | `jsIcZ` (Frame 41) | Basica, funcional |
| Detalle de articulo | **Falta** | - | Nueva pantalla |

### Gamificacion
| Elemento | Estado | Referencia .pen | Notas |
|----------|--------|-----------------|-------|
| Puntos en Home | Existe | `0Pg7a` (points-sec) | "1350 Earning Points" |
| Pantalla de resumen | **Falta** | - | Nueva pantalla |
| Logros / badges | **Falta** | - | Nuevo sistema |
| Racha visual | **Falta** | - | Nuevo componente |

### Perfil
| Elemento | Estado | Referencia .pen | Notas |
|----------|--------|-----------------|-------|
| Avatar en top bar | Existe | `rwjhf` (user-profile) | Solo icono, sin pantalla |
| Pantalla de perfil | **Falta** | - | Nueva pantalla |
| Configuracion | **Falta** | - | Nueva pantalla |

---

## Componentes: Existe vs Falta

| Componente | Estado | Prioridad |
|------------|--------|-----------|
| Top bar / Menu | Existe | - |
| Tab bar horizontal | Existe | - |
| Card modulo home | Existe | - |
| sec-book card | Existe | - |
| Article card | Existe | - |
| bt-read-chapter (boton) | Existe | - |
| user-profile avatar | Existe | - |
| Section header | Existe | - |
| Bottom navigation | **Falta** | Alta |
| Event card | **Falta** | Alta |
| Ticket card | **Falta** | Alta |
| Devocional card | **Falta** | Media |
| Track card | **Falta** | Media |
| Episode card | **Falta** | Baja |
| Input field | **Falta** | Alta (operador) |
| Text area | **Falta** | Alta (operador) |
| Select / Dropdown | **Falta** | Alta (operador) |
| Toggle | **Falta** | Media |
| Date/Time picker | **Falta** | Alta (operador) |
| Badge de estado | **Falta** | Alta (operador) |
| Progress bar | **Falta** | Media |
| Mini player audio | **Falta** | Baja |
| Player completo | **Falta** | Baja |
| Empty state | **Falta** | Media |

---

## Lo que Necesita Revision/Mejora (ya existe)

### Home (`app-home`)
- **Layout**: Usa posicionamiento absoluto (groups). Evaluar migrar a auto-layout para responsividad
- **Entry points**: Falta acceso claro a Devocional y Perfil
- **Bottom nav**: No existe, dificulta navegacion entre modulos
- **Tarjeta Events**: Solo muestra "Events / In 3 days", necesita ser mas informativa

### Biblia Listado (`app-bible-sec`)
- **Tabs Chapter y Verses**: Solo tienen estructura visual, falta funcionalidad/vista
- **Libros repetidos**: Hay Genesis repetido multiples veces (placeholder), necesita datos reales
- **Nombre "Knoledge"**: Typo en "Knowledge" (en tarjeta de home)
- **Nombre "hitorical"**: Typo en "historical" (encabezado NT)

### Articulos (`app-bible-articles`)
- **Falta pantalla detalle**: Al hacer tap en un articulo no hay a donde ir
- **Cards uniformes**: Los 5 article cards son identicos (lorem ipsum), necesitan contenido variado
- **Speaker avatares**: Todos usan el mismo avatar generico negro

---

## Plan de Accion Sugerido (Fases)

### Fase 1: Core (Prioridad Alta)
1. Pulir Home existente (layout, entry points, bottom nav)
2. Completar flujo Biblia (capitulos + lectura)
3. Disenar flujo completo de Eventos usuario (listado + detalle + checkout)
4. Disenar Mis Boletos

### Fase 2: Operador (Prioridad Alta)
5. Login operador
6. Dashboard operador
7. Flujo crear evento (3 pantallas)
8. Mis eventos + detalle

### Fase 3: Contenido (Prioridad Media)
9. Devocional (categorias + detalle)
10. Articulo detalle
11. Gamificacion resumen
12. Perfil usuario

### Fase 4: Complementario (Prioridad Baja)
13. Guest/Podcast (listado + reproductor)
14. Growth Tracks (listado + detalle)
15. Gestion boletos operador
16. Estadisticas operador

---

## Metricas de Completitud

```
Diseno actual:     ███░░░░░░░░░░░░░░░░░  ~10%
Post Fase 1:       ████████░░░░░░░░░░░░  ~35%
Post Fase 2:       ████████████░░░░░░░░  ~55%
Post Fase 3:       ████████████████░░░░  ~80%
Post Fase 4:       ████████████████████  100%
```
