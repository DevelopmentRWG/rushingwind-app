# Pantallas - App del Operador / Moderador

> Aplicacion para iglesias y organizadores que crean y gestionan eventos dentro de Rushing Wind.
> Todas las pantallas son **nuevas** (no existen en el diseno actual).

---

## Mapa de Navegacion

```
Login → Dashboard Operador
            ├── Crear Evento
            │   ├── Formulario (datos generales)
            │   ├── Configurar Boleteria
            │   └── Preview y Enviar a Aprobacion
            ├── Mis Eventos
            │   ├── Detalle / Editar Evento
            │   ├── Gestion de Boletos
            │   └── Estadisticas del Evento
            └── Perfil Organizador
                └── Configuracion
```

---

## 1. Login Operador

| Campo | Valor |
|-------|-------|
| Nombre | `op-login` |
| Estado | **Nueva** |
| Acceso | Punto de entrada de la app operador |

### Descripcion
Pantalla de autenticacion para organizadores/iglesias.

### Elementos principales
- Logo Rushing Wind
- Campo email
- Campo contrasena
- Boton "Iniciar Sesion"
- Link "Registrar mi organizacion"
- Posible login con Google/Apple

---

## 2. Dashboard Operador

| Campo | Valor |
|-------|-------|
| Nombre | `op-dashboard` |
| Estado | **Nueva** |
| Acceso | Post-login |

### Descripcion
Vista general del organizador con resumen de sus eventos y acciones rapidas.

### Elementos principales
- Saludo con nombre de la organizacion/iglesia
- Resumen rapido:
  - Eventos activos
  - Eventos pendientes de aprobacion
  - Boletos vendidos (total)
  - Proximo evento con countdown
- Boton principal "Crear Evento"
- Lista rapida de eventos recientes con estado
- Notificaciones (aprobaciones, ventas)

---

## 3. Crear Evento - Datos Generales

| Campo | Valor |
|-------|-------|
| Nombre | `op-create-event` |
| Estado | **Nueva** |
| Acceso | Dashboard → "Crear Evento" |

### Descripcion
Formulario para ingresar la informacion basica del evento.

### Elementos principales
- Titulo del evento
- Descripcion (texto largo)
- Subir imagen/arte del evento
- Fecha y hora de inicio
- Fecha y hora de fin
- Ubicacion (direccion, ciudad, pais)
- Tipo de evento (conferencia, concierto, retiro, culto, otro)
- Boton "Siguiente: Configurar Boleteria"

---

## 4. Crear Evento - Configurar Boleteria

| Campo | Valor |
|-------|-------|
| Nombre | `op-create-tickets` |
| Estado | **Nueva** |
| Acceso | Crear Evento Datos → "Siguiente" |

### Descripcion
Configuracion de tipos de boleto, precios y capacidad.

### Elementos principales
- Evento gratis toggle (si/no)
- Lista de tipos de boleto:
  - Nombre del tipo (ej: "General", "VIP", "Early Bird")
  - Precio
  - Cantidad disponible
  - Boton agregar tipo de boleto
- Fecha limite de venta
- Boton "Siguiente: Preview"

---

## 5. Crear Evento - Preview y Enviar

| Campo | Valor |
|-------|-------|
| Nombre | `op-event-preview` |
| Estado | **Nueva** |
| Acceso | Configurar Boleteria → "Siguiente" |

### Descripcion
Vista previa de como se vera el evento para los usuarios, con opcion de enviarlo a aprobacion.

### Elementos principales
- Preview del evento tal como lo vera el usuario (card + detalle)
- Resumen de boleteria configurada
- Mensaje informativo: "Tu evento sera revisado por el equipo de Rushing Wind antes de ser publicado"
- Boton "Enviar a Aprobacion"
- Boton "Guardar Borrador"
- Boton "Editar"

---

## 6. Mis Eventos

| Campo | Valor |
|-------|-------|
| Nombre | `op-my-events` |
| Estado | **Nueva** |
| Acceso | Dashboard → "Mis Eventos" o tab de navegacion |

### Descripcion
Listado de todos los eventos creados por el organizador con su estado actual.

### Elementos principales
- Filtro por estado: Todos | Borrador | Pendiente | Aprobado | Rechazado | Finalizado
- Tarjetas de evento con:
  - Imagen miniatura
  - Titulo
  - Fecha
  - Estado (badge de color):
    - Borrador (gris)
    - Pendiente de aprobacion (amarillo)
    - Aprobado / Publicado (verde)
    - Rechazado (rojo) + motivo
    - Finalizado (neutro)
  - Boletos vendidos / total
- Acciones: Editar, Ver estadisticas, Duplicar

---

## 7. Detalle / Editar Evento

| Campo | Valor |
|-------|-------|
| Nombre | `op-event-detail` |
| Estado | **Nueva** |
| Acceso | Mis Eventos → tap en evento |

### Descripcion
Vista completa del evento con posibilidad de edicion (si no esta publicado).

### Elementos principales
- Toda la informacion del evento (misma que en creacion)
- Estado actual con timeline:
  - Creado → Enviado → En revision → Aprobado → Publicado
- Si fue rechazado: motivo del rechazo y boton "Editar y Reenviar"
- Boton "Editar" (si es borrador o rechazado)
- Boton "Cancelar Evento" (si esta publicado)
- Enlace para compartir el evento

---

## 8. Gestion de Boletos

| Campo | Valor |
|-------|-------|
| Nombre | `op-ticket-management` |
| Estado | **Nueva** |
| Acceso | Detalle Evento → "Gestionar Boletos" |

### Descripcion
Vista de todos los boletos vendidos para un evento especifico.

### Elementos principales
- Resumen: vendidos / disponibles por tipo
- Barra de progreso visual de venta
- Lista de compradores:
  - Nombre del comprador
  - Tipo de boleto
  - Fecha de compra
  - Estado (valido / usado / cancelado)
- Busqueda por nombre
- Exportar lista (CSV)
- Check-in: validar boleto por codigo/QR

---

## 9. Estadisticas del Evento

| Campo | Valor |
|-------|-------|
| Nombre | `op-event-stats` |
| Estado | **Nueva** |
| Acceso | Detalle Evento → "Estadisticas" |

### Descripcion
Metricas y datos del rendimiento del evento.

### Elementos principales
- Boletos vendidos vs capacidad total
- Ingresos totales
- Ventas por tipo de boleto (grafico)
- Ventas por dia (grafico de linea)
- Vistas del evento en la app (cuantos usuarios lo vieron)
- Tasa de conversion (vistas → compras)

---

## 10. Perfil Organizador

| Campo | Valor |
|-------|-------|
| Nombre | `op-profile` |
| Estado | **Nueva** |
| Acceso | Dashboard → icono perfil |

### Descripcion
Datos de la organizacion/iglesia con configuracion de cuenta.

### Elementos principales
- Logo/avatar de la organizacion
- Nombre de la organizacion
- Descripcion / bio
- Informacion de contacto
- Historial de eventos (total creados, total asistentes)
- Metodo de pago para recibir ingresos de boleteria
- Configuracion de notificaciones
- Cerrar sesion

---

## Resumen de Pantallas

| # | Pantalla | Prioridad |
|---|----------|-----------|
| 1 | Login Operador | Alta |
| 2 | Dashboard Operador | Alta |
| 3 | Crear Evento - Datos | Alta |
| 4 | Crear Evento - Boleteria | Alta |
| 5 | Crear Evento - Preview | Alta |
| 6 | Mis Eventos | Alta |
| 7 | Detalle / Editar Evento | Alta |
| 8 | Gestion de Boletos | Media |
| 9 | Estadisticas del Evento | Media |
| 10 | Perfil Organizador | Media |

**Total: 10 pantallas** (todas nuevas)

---

## Notas

- El dashboard de administracion **de Rushing Wind** (para aprobar/rechazar eventos) ya existe como sistema externo. No se incluye aqui.
- La app del operador es independiente de la app del usuario pero comparte identidad visual.
- Un operador tambien puede ser usuario de la app principal (misma cuenta, diferente app/vista).
