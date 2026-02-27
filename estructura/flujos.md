# Flujos de Usuario

> Flujos principales de interaccion para ambas aplicaciones (usuario y operador).

---

## App del Usuario

### Flujo 1: Leer la Biblia

```
Home
  └─ Tap tarjeta "Bible"
      └─ Biblia - Listado de Libros (tab "All Books")
          ├─ Scroll por secciones (AT / NT)
          └─ Tap en libro (ej: Genesis)
              └─ Capitulos del Libro
                  ├─ Ver progreso (50/50)
                  └─ Tap en capitulo
                      └─ Lectura (versiculos)
                          ├─ Leer contenido
                          ├─ Navegar capitulo anterior/siguiente
                          └─ Marcar como leido
                              └─ +Puntos (gamificacion)
                                  └─ Regreso a Capitulos (progreso actualizado)
```

**Pantallas involucradas**: Home → app-bible-sec → app-bible-chapters (nueva) → app-bible-reading (nueva)

**Puntos clave**:
- El boton "Read now" en cada libro lleva directo al ultimo capitulo no leido
- Marcar capitulo como leido actualiza progreso del libro y gamificacion
- Al terminar un libro completo: logro desbloqueado

---

### Flujo 2: Descubrir y comprar boleto de evento

```
Home
  └─ Tap tarjeta "Events" (o proximo evento)
      └─ Eventos - Listado
          ├─ Scroll por eventos disponibles
          ├─ Filtrar por fecha/ubicacion/tipo
          └─ Tap en evento
              └─ Evento - Detalle
                  ├─ Ver info completa (fecha, lugar, organizador)
                  ├─ Ver tipos de boleto y precios
                  └─ Tap "Comprar Boleto"
                      └─ Evento - Checkout
                          ├─ Seleccionar tipo y cantidad
                          ├─ Metodo de pago
                          └─ Confirmar compra
                              └─ Boleto generado (QR/codigo)
                                  └─ Visible en Mis Boletos (perfil)
```

**Pantallas involucradas**: Home → app-events (nueva) → app-event-detail (nueva) → app-event-checkout (nueva)

**Puntos clave**:
- Desde home, la tarjeta de evento muestra countdown ("In 3 days")
- El listado prioriza eventos proximos
- Post-compra: el boleto aparece en "Mis Boletos" en el perfil
- Asistir al evento otorga puntos de gamificacion

---

### Flujo 3: Consumir devocional

```
Home
  └─ Tap seccion devocional (entry point por definir)
      └─ Devocional - Categorias
          ├─ Ver devocional del dia (hero card)
          ├─ Seleccionar categoria (Jovenes, Mujeres, Matrimonio...)
          └─ Tap en devocional
              └─ Devocional - Detalle
                  ├─ Ver info del creador
                  ├─ Consumir contenido (texto / audio / video)
                  └─ Tap "Completar"
                      └─ +Puntos (gamificacion)
```

**Pantallas involucradas**: Home → app-devocional (nueva) → app-devocional-detail (nueva)

**Puntos clave**:
- El entry point desde home necesita definirse (tarjeta dedicada o integracion con "Bible Articles")
- Completar devocional alimenta la racha diaria
- Multiples creadores generan contenido para diferentes segmentos

---

### Flujo 4: Escuchar podcast / Guest

```
Home
  └─ Tap tarjeta "Guest"
      └─ Guest - Listado de Episodios
          ├─ Ver episodio destacado
          └─ Tap en episodio
              └─ Guest - Reproductor
                  ├─ Reproducir audio/video
                  ├─ Controles (play, pause, avanzar, retroceder)
                  └─ Mini player persiste al navegar a otras pantallas
```

**Pantallas involucradas**: Home → app-guest (nueva) → app-guest-player (nueva)

**Puntos clave**:
- El mini player debe ser persistente (no se pierde al cambiar de pantalla)
- Escuchar episodio completo otorga puntos

---

### Flujo 5: Avanzar en Growth Track

```
Home
  └─ Tap tarjeta "Growth Tracks" o "Knowledge Tracks"
      └─ Growth Tracks - Listado
          ├─ Ver progreso global (12/26 completed)
          └─ Tap en track
              └─ Growth Track - Detalle
                  ├─ Ver lista de dias (completado / actual / bloqueado)
                  └─ Tap en dia actual
                      ├─ Consumir contenido del dia
                      └─ Tap "Completar Dia"
                          └─ +Puntos + racha actualizada
                              └─ Siguiente dia desbloqueado
```

**Pantallas involucradas**: Home → app-growth-tracks (nueva) → app-growth-track-detail (nueva)

---

### Flujo 6: Leer articulo biblico

```
Home
  └─ Tap tarjeta "Bible Articles"
      └─ Articulos - Listado
          ├─ Buscar por tema
          └─ Tap en articulo
              └─ Articulo - Detalle (nueva)
                  ├─ Leer contenido completo
                  ├─ Ver info del speaker
                  └─ Tap "Completar"
                      └─ +Puntos
```

**Pantallas involucradas**: Home → app-bible-articles (existe) → app-article-detail (nueva)

---

### Flujo 7: Ver perfil y boletos

```
Home
  └─ Tap avatar en top bar
      └─ Perfil
          ├─ Ver resumen (puntos, racha, stats)
          ├─ Tap "Mis Boletos"
          │   └─ Mis Boletos
          │       ├─ Filtrar proximos / pasados
          │       └─ Tap en boleto → ver QR/codigo
          └─ Tap "Configuracion"
              └─ Ajustes (notificaciones, idioma, tema)
```

**Pantallas involucradas**: Home → app-profile (nueva) → app-my-tickets (nueva)

---

## App del Operador

### Flujo 8: Crear y publicar evento

```
Login Operador
  └─ Dashboard
      └─ Tap "Crear Evento"
          └─ Crear Evento - Datos Generales
              ├─ Llenar formulario (titulo, descripcion, fecha, lugar)
              ├─ Subir imagen
              └─ Tap "Siguiente"
                  └─ Crear Evento - Configurar Boleteria
                      ├─ Definir tipos de boleto y precios
                      └─ Tap "Siguiente"
                          └─ Crear Evento - Preview
                              ├─ Revisar como se ve
                              └─ Tap "Enviar a Aprobacion"
                                  └─ Evento cambia a estado "Pendiente"
                                      └─ Rushing Wind revisa y aprueba/rechaza
                                          ├─ Aprobado → publicado para usuarios
                                          └─ Rechazado → motivo + opcion de editar y reenviar
```

**Pantallas involucradas**: op-login → op-dashboard → op-create-event → op-create-tickets → op-event-preview

**Puntos clave**:
- El proceso de aprobacion es externo (dashboard admin de Rushing Wind)
- El operador recibe notificacion del resultado
- Eventos rechazados pueden ser editados y reenviados

---

### Flujo 9: Gestionar evento publicado

```
Dashboard
  └─ Tap en evento activo (o ir a "Mis Eventos")
      └─ Mis Eventos
          └─ Tap en evento publicado
              └─ Detalle del Evento
                  ├─ Ver estado y timeline
                  ├─ Tap "Gestionar Boletos"
                  │   └─ Gestion de Boletos
                  │       ├─ Ver vendidos vs disponibles
                  │       ├─ Buscar comprador
                  │       └─ Check-in (validar QR en el evento)
                  └─ Tap "Estadisticas"
                      └─ Estadisticas del Evento
                          └─ Ver metricas (ventas, ingresos, vistas)
```

**Pantallas involucradas**: op-dashboard → op-my-events → op-event-detail → op-ticket-management / op-event-stats

---

## Resumen de Flujos

| # | Flujo | App | Pantallas | Prioridad |
|---|-------|-----|-----------|-----------|
| 1 | Leer la Biblia | Usuario | 4 | Alta |
| 2 | Descubrir y comprar boleto | Usuario | 4 | Alta |
| 3 | Consumir devocional | Usuario | 3 | Media |
| 4 | Escuchar podcast | Usuario | 3 | Baja |
| 5 | Avanzar en Growth Track | Usuario | 3 | Media-Baja |
| 6 | Leer articulo biblico | Usuario | 3 | Media |
| 7 | Ver perfil y boletos | Usuario | 3 | Media |
| 8 | Crear y publicar evento | Operador | 5 | Alta |
| 9 | Gestionar evento publicado | Operador | 4 | Media |
