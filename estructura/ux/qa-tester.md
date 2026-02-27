# Guia de Rol: QA Tester

> Casos de prueba, criterios de aceptacion y validacion de calidad para Rushing Wind App.

---

## Objetivo del Rol

Garantizar que ambas aplicaciones (usuario y operador) funcionen correctamente, cumplan los criterios de aceptacion de cada flujo, y mantengan fidelidad visual con los disenos aprobados. El QA Tester valida funcionalidad, usabilidad, rendimiento y consistencia en cada fase de desarrollo.

---

## Entregables Esperados

| Entregable | Formato | Descripcion |
|------------|---------|-------------|
| Plan de pruebas por fase | Documento | Alcance, tipos de test, prioridades por cada fase de desarrollo |
| Casos de prueba por modulo | Documento / spreadsheet | Escenarios detallados con pasos, datos de entrada y resultado esperado |
| Criterios de aceptacion por pantalla | Documento | Condiciones que debe cumplir cada pantalla para considerarse completa |
| Reporte de bugs | Issue tracker | Bugs categorizados por severidad con pasos para reproducir y evidencia |
| Checklist de revision visual | Documento | Validacion de fidelidad al diseno por pantalla (colores, tipografia, espaciado, estados) |
| Reporte de regresion | Documento | Validacion de que funcionalidad existente no se rompe al agregar nueva |

---

## Tareas por Fase

### Fase 1: Core (Prioridad Alta)

**Foco: Home + Biblia + Eventos + Boleteria usuario**

#### Home (`app-home`)
- Verificar que todas las tarjetas de modulo son visibles y tienen el contenido correcto
- Verificar que los entry points navegan a la pantalla correcta
- Verificar que los datos dinamicos se muestran correctamente (puntos, proximo evento, progreso)
- Verificar bottom navigation: cada tab navega al modulo correspondiente, indicador activo funciona
- Verificar que los textos no tienen typos (comprobar correccion de "Knoledge" y "hitorical")

#### Biblia - Listado de Libros (`app-bible-sec`)
- Verificar que los 66 libros se muestran organizados por seccion (AT/NT)
- Verificar tabs (All Books / Chapter / Verses) — navegan a la vista correspondiente
- Verificar que cada tarjeta de libro muestra: nombre, numero, progreso de capitulos, tiempo estimado
- Verificar scroll — el listado completo es accesible sin cortes
- Verificar boton "Read now" — navega al ultimo capitulo no leido del libro

#### Biblia - Capitulos (`app-bible-chapters`)
- Verificar grid de capitulos con numeros correctos para cada libro
- Verificar estados visuales: leido (indicador), no leido (default), en progreso (indicador parcial)
- Verificar que al marcar un capitulo como leido se actualiza el estado visual
- Verificar navegacion back → regresa al listado de libros

#### Biblia - Lectura (`app-bible-reading`)
- Verificar que los versiculos se muestran numerados correctamente
- Verificar navegacion entre capitulos (anterior/siguiente)
- Verificar boton "Marcar como leido" → actualiza progreso del libro y puntos de gamificacion
- Verificar legibilidad del texto (tamano, espaciado, contraste en tema oscuro)

#### Eventos - Listado (`app-events`)
- Verificar que los eventos publicados se muestran ordenados por fecha
- Verificar filtros (fecha, ubicacion, tipo) — filtran correctamente y se pueden combinar
- Verificar que Event Card muestra: imagen, titulo, fecha, ubicacion, precio
- Verificar Empty State cuando no hay eventos disponibles

#### Eventos - Detalle (`app-event-detail`)
- Verificar que toda la informacion del evento se muestra completa
- Verificar tipos de boleto disponibles con precios correctos
- Verificar boton "Comprar Boleto" navega al checkout
- Verificar funcion de compartir evento

#### Eventos - Checkout (`app-event-checkout`)
- Verificar seleccion de tipo y cantidad de boleto
- Verificar calculo correcto del total
- Verificar flujo de pago completo (integracion con pasarela)
- Verificar pantalla de confirmacion con boleto generado (QR/codigo)
- Verificar que el boleto aparece en "Mis Boletos" post-compra
- **Caso edge**: intentar comprar mas boletos que los disponibles
- **Caso edge**: fallo en el pago — mensaje de error claro, no se genera boleto

#### Mis Boletos (`app-my-tickets`)
- Verificar listado de boletos con datos correctos (evento, fecha, tipo, estado)
- Verificar filtro proximos / pasados
- Verificar que el QR/codigo del boleto se muestra y es escaneable
- Verificar Empty State cuando no hay boletos

### Fase 2: Operador (Prioridad Alta)

**Foco: App operador completa**

#### Login Operador (`op-login`)
- Verificar login con credenciales validas → navega al dashboard
- Verificar login con credenciales invalidas → mensaje de error claro
- Verificar campos vacios → validacion impide envio
- Verificar persistencia de sesion (no pide login cada vez)

#### Dashboard (`op-dashboard`)
- Verificar que las metricas reflejan datos reales (eventos activos, pendientes, boletos vendidos)
- Verificar boton "Crear Evento" navega al formulario
- Verificar lista de eventos recientes con estado correcto

#### Crear Evento — Datos Generales (`op-create-event`)
- Verificar todos los campos del formulario (titulo, descripcion, imagen, fecha, ubicacion, tipo)
- Verificar validaciones: campos obligatorios, formato de fechas, tamano de imagen
- Verificar que "Siguiente" solo es posible si los campos obligatorios estan completos
- **Caso edge**: texto extremadamente largo en titulo o descripcion

#### Crear Evento — Boleteria (`op-create-tickets`)
- Verificar toggle evento gratis (desactiva campos de precio)
- Verificar agregar multiples tipos de boleto
- Verificar validaciones: precio > 0, cantidad > 0
- Verificar eliminar un tipo de boleto de la lista
- **Caso edge**: crear evento sin ningun tipo de boleto

#### Crear Evento — Preview (`op-event-preview`)
- Verificar que la preview muestra el evento tal como lo vera el usuario
- Verificar boton "Enviar a Aprobacion" — cambia estado a pendiente
- Verificar boton "Guardar Borrador" — guarda sin enviar
- Verificar boton "Editar" — regresa al formulario con datos prellenados

#### Mis Eventos (`op-my-events`)
- Verificar filtros por estado (Todos, Borrador, Pendiente, Aprobado, Rechazado, Finalizado)
- Verificar Badge de Estado con color correcto por estado
- Verificar que eventos rechazados muestran el motivo
- Verificar acciones: editar, ver estadisticas

#### Workflow de Aprobacion
- Verificar transicion de estados: borrador → enviado → en_revision → aprobado/rechazado
- Verificar que al aprobar, el evento aparece en el listado de la app de usuario
- Verificar que al rechazar, el operador recibe motivo y puede editar y reenviar
- Verificar notificaciones al operador en cada cambio de estado

### Fase 3: Contenido (Prioridad Media)

**Foco: Devocional, Articulos, Gamificacion, Perfil**

#### Devocional
- Verificar categorias se muestran correctamente (Mujeres, Jovenes, etc.)
- Verificar hero card del devocional del dia
- Verificar detalle: contenido multimedia (texto/audio/video) se reproduce correctamente
- Verificar boton "Completar" → suma puntos de gamificacion

#### Articulos
- Verificar busqueda por tema funciona
- Verificar detalle: contenido largo, speaker info, articulos relacionados
- Verificar boton "Completar" → suma puntos

#### Gamificacion
- Verificar que los puntos se acumulan correctamente por cada actividad
- Verificar calculo de racha (dias consecutivos)
- Verificar desglose por modulo
- Verificar badges/logros se desbloquean al cumplir criterios
- **Caso edge**: perdida de racha — el contador se reinicia correctamente

#### Perfil
- Verificar datos del usuario (nombre, avatar, estadisticas)
- Verificar edicion de perfil (cambiar nombre, subir avatar)
- Verificar acceso a "Mis Boletos" desde perfil
- Verificar configuracion (notificaciones, idioma, tema)
- Verificar cerrar sesion → regresa a login

### Fase 4: Complementario (Prioridad Baja)

**Foco: Podcast, Growth Tracks, pantallas restantes operador**

#### Guest/Podcast
- Verificar listado de episodios con datos correctos
- Verificar reproductor: play, pause, avanzar, retroceder, barra de progreso
- Verificar mini player persiste al navegar entre pantallas
- Verificar que escuchar episodio completo suma puntos

#### Growth Tracks
- Verificar listado de tracks con progreso global
- Verificar detalle: dias con estados (completado, actual, bloqueado)
- Verificar "Completar Dia" → desbloquea siguiente dia, suma puntos, actualiza racha

#### Gestion de Boletos Operador (`op-ticket-management`)
- Verificar listado de compradores con datos correctos
- Verificar busqueda por nombre
- Verificar check-in por QR → cambia estado del boleto a "usado"
- Verificar exportar CSV contiene todos los datos

#### Estadisticas Operador (`op-event-stats`)
- Verificar que los graficos reflejan datos reales
- Verificar metricas: boletos vendidos, ingresos, conversion

---

## Tipos de Testing Transversales

| Tipo | Descripcion | Frecuencia |
|------|-------------|------------|
| **Funcional** | Cada pantalla y flujo cumple su proposito | Por feature |
| **Visual** | Fidelidad al diseno (colores, tipografia, espaciado, estados) | Por pantalla |
| **Responsividad** | Se ve correctamente en diferentes tamanos de pantalla | Por pantalla |
| **Tema oscuro/claro** | Ambos temas se ven correctos (si se implementa dual) | Por pantalla |
| **Edge cases** | Datos vacios, textos largos, conexion lenta, sin conexion | Por modulo |
| **Regresion** | Funcionalidad existente no se rompe al agregar nueva | Por fase |
| **Rendimiento** | Listas largas (66 libros, muchos eventos) cargan fluido | Por fase |
| **Accesibilidad** | Contraste, tamano de texto, targets de tap suficientes | Por fase |

---

## Dependencias

| Dependo de... | Para... |
|---------------|---------|
| **UI Designer** | Disenos aprobados como referencia visual para validacion |
| **Frontend Developer** | Builds funcionales para ejecutar pruebas |
| **Backend Developer** | APIs funcionales y datos de prueba |
| **UX Researcher** | Criterios de exito de cada flujo, personas para escenarios de prueba |

| Dependen de mi... | Porque... |
|--------------------|-----------|
| **Todo el equipo** | Los reportes de bugs y validaciones determinan si una feature esta lista para produccion |
| **Cliente (Rushing Wind)** | La validacion de QA es la ultima capa de confianza antes del lanzamiento |

---

## Referencias

| Documento | Relevancia |
|-----------|------------|
| `estructura/flujos.md` | 9 flujos principales — base para escenarios de prueba end-to-end |
| `estructura/pantallas-usuario.md` | 18 pantallas usuario — checklist de elementos a verificar |
| `estructura/pantallas-operador.md` | 10 pantallas operador — checklist de elementos a verificar |
| `estructura/componentes.md` | Catalogo de componentes — verificar estados y variantes |
| `estructura/gap-analysis.md` | Estado actual vs deseado — contexto para tests de regresion |
| `estructura/requerimientos.md` | Funcionalidades requeridas — criterios de aceptacion de alto nivel |
| `pencil-new.pen` | Diseno actual — referencia visual |
