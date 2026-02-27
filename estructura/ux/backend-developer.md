# Guia de Rol: Backend Developer

> APIs, base de datos, autenticacion, pagos y CMS para la plataforma Rushing Wind.

---

## Objetivo del Rol

Disenar e implementar la infraestructura de backend que soporte ambas aplicaciones (usuario y operador), incluyendo APIs RESTful, base de datos, autenticacion, sistema de pagos para boleteria, gestion de contenido y el flujo de aprobacion de eventos. El backend debe ser escalable para soportar multiples iglesias/organizadores creando contenido simultaneamente.

---

## Entregables Esperados

| Entregable | Formato | Descripcion |
|------------|---------|-------------|
| Esquema de base de datos | Migraciones / diagrama ER | Tablas para usuarios, contenido biblico, eventos, boletos, gamificacion, operadores |
| APIs RESTful documentadas | Endpoints + docs (OpenAPI/Swagger) | CRUD completo para todos los modulos |
| Sistema de autenticacion | Codigo | Login/registro para usuarios y operadores, sesiones, tokens |
| Integracion de pagos | Codigo | Pasarela de pago para compra de boletos |
| Sistema de aprobacion de eventos | Codigo | Workflow: creado → enviado → en revision → aprobado/rechazado |
| CMS para contenido | Codigo/Configuracion | Gestion de devocionales, articulos, episodios, growth tracks |
| Sistema de notificaciones | Codigo | Push notifications para eventos, aprobaciones, recordatorios |

---

## Tareas por Fase

### Fase 1: Core (Prioridad Alta)

**Foco: Fundamento + Biblia + Eventos + Boleteria**

- **Fundamento**:
  - Disenar esquema de base de datos inicial (usuarios, roles, sesiones)
  - Configurar autenticacion: registro, login, tokens refresh, roles (usuario vs operador)
  - Configurar almacenamiento de archivos (imagenes de eventos, avatares)
  - Configurar infraestructura base (servidor, base de datos, entorno de staging)
- **API de Biblia**:
  - Modelo de datos: Testamentos → Libros → Capitulos → Versiculos
  - Endpoint: listado de libros con metadata (nombre, capitulos totales, seccion, tiempo estimado)
  - Endpoint: capitulos de un libro
  - Endpoint: versiculos de un capitulo
  - Endpoint: progreso del usuario (capitulos leidos, porcentaje por libro)
  - Endpoint: marcar capitulo como leido → actualizar progreso y puntos
- **API de Eventos**:
  - Modelo de datos: Evento (titulo, descripcion, imagen, fecha, ubicacion, organizador, estado, tipos de boleto)
  - Endpoint: listado de eventos publicados (con filtros: fecha, ubicacion, tipo)
  - Endpoint: detalle de un evento
  - Endpoint: crear evento (operador)
  - Endpoint: actualizar evento / reenviar a aprobacion
  - Endpoint: cambiar estado del evento (workflow de aprobacion)
  - Validaciones: campos obligatorios, formato de fechas, tamano de imagen
- **API de Boleteria**:
  - Modelo de datos: TipoBoleto (nombre, precio, cantidad), Boleto (comprador, tipo, estado, codigo QR)
  - Endpoint: tipos de boleto disponibles por evento
  - Endpoint: comprar boleto (crear transaccion + generar codigo)
  - Endpoint: mis boletos (usuario)
  - Integracion con pasarela de pago (Stripe o similar)
  - Generacion de codigos QR unicos por boleto
- **API de Gamificacion (base)**:
  - Modelo de datos: PuntosUsuario, HistorialActividad, Racha
  - Endpoint: obtener puntos y racha del usuario
  - Logica: sumar puntos por actividad (capitulo leido, evento asistido)
  - Logica: calcular racha de dias consecutivos

### Fase 2: Operador (Prioridad Alta)

**Foco: APIs especificas para la app del operador**

- **API de Operador / Organizacion**:
  - Modelo de datos: Organizacion (nombre, logo, descripcion, contacto, metodo de pago)
  - Endpoint: registro de organizacion
  - Endpoint: perfil del operador (ver/editar)
  - Endpoint: dashboard — resumen de eventos activos, pendientes, boletos vendidos
- **Workflow de aprobacion**:
  - Estados del evento: borrador → enviado → en_revision → aprobado / rechazado
  - Endpoint: enviar evento a aprobacion
  - Endpoint: aprobar/rechazar evento (admin de Rushing Wind — conectar con dashboard externo existente)
  - Notificacion al operador cuando cambia el estado
  - Si rechazado: almacenar motivo, permitir edicion y reenvio
- **API de Gestion de Boletos (operador)**:
  - Endpoint: boletos vendidos por evento (con paginacion y busqueda)
  - Endpoint: validar boleto (check-in por codigo QR)
  - Endpoint: exportar lista de asistentes (CSV)
  - Endpoint: estadisticas del evento (vendidos vs capacidad, ingresos, ventas por dia)
- **Notificaciones para operador**:
  - Nuevo boleto vendido
  - Evento aprobado/rechazado
  - Recordatorio antes del evento

### Fase 3: Contenido (Prioridad Media)

**Foco: Devocional, Articulos, Gamificacion completa, Perfil**

- **API de Devocional**:
  - Modelo de datos: Devocional (titulo, contenido, tipo [texto/audio/video], categoria, creador)
  - Modelo de datos: CategoriaDevocional (Mujeres, Jovenes, Ninos, Matrimonio, General)
  - Endpoint: listado por categoria
  - Endpoint: devocional del dia
  - Endpoint: detalle del devocional
  - Endpoint: marcar como completado → sumar puntos
- **API de Articulos Biblicos**:
  - Modelo de datos: Articulo (titulo, contenido, speaker, duracion, tema)
  - Endpoint: listado con busqueda por tema
  - Endpoint: detalle del articulo
  - Endpoint: marcar como completado → sumar puntos
  - Endpoint: articulos relacionados
- **API de Gamificacion (completa)**:
  - Modelo de datos: Logro/Badge (nombre, descripcion, icono, criterio)
  - Endpoint: logros del usuario (obtenidos y pendientes)
  - Endpoint: desglose de puntos por modulo
  - Endpoint: historial de actividad reciente
  - Logica: desbloquear logros automaticamente al cumplir criterios
- **API de Perfil de Usuario**:
  - Endpoint: datos del perfil (nombre, avatar, estadisticas)
  - Endpoint: actualizar perfil / avatar
  - Endpoint: configuracion (notificaciones, idioma, tema)
  - Endpoint: eliminar cuenta

### Fase 4: Complementario (Prioridad Baja)

**Foco: Podcast, Growth Tracks, APIs restantes**

- **API de Guest/Podcast**:
  - Modelo de datos: Episodio (titulo, invitado, audio/video URL, duracion, miniatura)
  - Endpoint: listado de episodios (con paginacion)
  - Endpoint: detalle del episodio
  - Endpoint: marcar como escuchado → sumar puntos
  - Streaming de audio/video (CDN)
- **API de Growth Tracks**:
  - Modelo de datos: Track (nombre, dias totales, tema), DiaTrack (contenido, orden)
  - Endpoint: listado de tracks con progreso del usuario
  - Endpoint: detalle del track (dias con estado)
  - Endpoint: completar dia → sumar puntos, actualizar racha, desbloquear siguiente dia
- **CMS / Gestion de Contenido**:
  - Interfaz o endpoints para que los creadores suban devocionales, articulos, episodios
  - Moderacion de contenido (si aplica)
  - Versionado de contenido
- **Estadisticas avanzadas del operador**:
  - Endpoint: conversion (vistas → compras)
  - Endpoint: vistas del evento en la app
  - Endpoint: comparativa entre eventos del mismo operador

---

## Consideraciones Tecnicas

- **Dos apps, un backend**: ambas aplicaciones consumen las mismas APIs, diferenciadas por rol/permisos
- **Dashboard admin existente**: ya existe un dashboard externo para aprobar/rechazar eventos — el backend debe integrarse con el, no reemplazarlo
- **Equipo anterior (Beirut)**: revisar que infraestructura y datos existentes hay. Evaluar si se migra o se reconstruye
- **Pagos**: la pasarela debe manejar comisiones (porcentaje para Rushing Wind + porcentaje para el organizador)
- **Contenido biblico**: es estatico (no cambia) — evaluar precargar en la app vs servir por API
- **Escalabilidad**: multiples organizadores creando eventos simultaneamente, picos de venta de boletos

---

## Dependencias

| Dependo de... | Para... |
|---------------|---------|
| **UI Designer** | Estructura de datos implicita en las pantallas y formularios |
| **UX Researcher** | Flujos validados que definen los endpoints necesarios |
| **Cliente (Rushing Wind)** | Acceso a infraestructura existente, datos actuales, pasarela de pago preferida |

| Dependen de mi... | Porque... |
|--------------------|-----------|
| **Frontend Developer** | Las APIs son la fuente de datos para toda la UI |
| **QA Tester** | Los endpoints necesitan tests de integracion y los datos definen los escenarios de prueba |

---

## Referencias

| Documento | Relevancia |
|-----------|------------|
| `estructura/requerimientos.md` | Funcionalidades por modulo, restricciones tecnicas |
| `estructura/modulos.md` | 7 modulos con funcionalidades detalladas — base para el esquema de datos |
| `estructura/flujos.md` | 9 flujos que definen las transacciones y endpoints necesarios |
| `estructura/pantallas-operador.md` | Pantallas del operador — definen los datos y acciones del backend |
| `estructura/pantallas-usuario.md` | Pantallas del usuario — definen los datos a consumir |
| `estructura/componentes.md` | Componentes que informan la estructura de las respuestas de API |
