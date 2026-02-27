# Requerimientos - Rushing Wind App

> Fuente: Transcripciones de reuniones (primer y segundo acercamiento)

---

## 1. Vision del Producto

Rushing Wind es un **movimiento** cuyo objetivo es **promover, propagar y difundir el evangelio**. La app es la herramienta digital central de ese movimiento.

En su nucleo es una **Biblia moderna para Generacion Z** con devocional integrado, pero se extiende a ser una **plataforma de eventos/boleteria** donde iglesias y organizadores cristianos pueden publicar sus propios eventos ante toda la base de usuarios.

---

## 2. Publico Objetivo

- **Generacion Z** como audiencia principal
- Cultura cristiana (no catolica tradicional): participativa, moderna, diversa
- Iglesias y comunidades cristianas de **Norteamerica y Latinoamerica**
- Creadores de contenido cristiano (predicadores, speakers, artistas)

---

## 3. Dos Aplicaciones

La plataforma se compone de **dos aplicaciones** diferenciadas:

### 3.1 App del Usuario
- Consumir la Biblia (lectura, estudio, progreso)
- Acceder a contenido devocional premium por temas
- Descubrir y asistir a eventos
- Consumir contenido de creadores (articulos, podcasts, tracks)
- Gamificacion (puntos, progreso, rachas)

### 3.2 App del Operador / Moderador
- Crear y gestionar eventos propios
- Subir eventos a la plataforma para que todos los usuarios los vean
- Gestionar boleteria de sus eventos
- Comunicacion con el equipo de Rushing Wind para autorizacion

---

## 4. Requerimientos Funcionales

### 4.1 Modulo Biblia (Principal)
- Lectura de la Biblia completa (66 libros)
- Navegacion por: Libros → Capitulos → Versiculos
- Separacion por Antiguo y Nuevo Testamento
- Progreso de lectura por libro (ej: 50/50 capitulos)
- Tiempo estimado de lectura
- Interfaz moderna, no tradicional

### 4.2 Modulo Devocional
- Contenido devocional premium
- Segmentado por temas: mujeres, jovenes, ninos, bebes, matrimonio
- Creadores/predicadores modernos generan los call-to-action devocionales
- Conexion personal con Dios como objetivo del modulo
- Tendencias emergentes en comunicacion de temas

### 4.3 Modulo Eventos / Boleteria
- **Cualquier persona/iglesia puede crear su propio evento**
- El evento se publica para que todos los usuarios lo vean
- Sistema de autorizacion: Rushing Wind aprueba eventos antes de publicar
  - Filtro para que no se publiquen eventos no cristianos
  - Contacto entre organizador y equipo de Rushing Wind
- Boleteria integrada (compra de boletos)
- Informacion del evento: titulo, fecha, descripcion, ubicacion

### 4.4 Modulo Guest / Podcast
- Episodios de contenido invitado
- Nuevos episodios frecuentes
- Reproductor de audio/video

### 4.5 Modulo Growth Tracks
- Tracks de crecimiento espiritual
- Progreso por dias (ej: "5 days")
- Conteo de tracks completados (ej: "12/26 completed")

### 4.6 Modulo Articulos Biblicos
- Enciclopedia biblica con articulos explicativos
- Busqueda por tema
- Speakers/autores con nombre y avatar
- Duracion estimada de lectura
- Tarjetas con descripcion previa del articulo

### 4.7 Gamificacion
- Sistema de puntos ("Earning Points")
- Acumulacion por actividad (lectura, devocionales, asistencia)
- Racha de dias consecutivos
- Progreso visible en el home

---

## 5. Requerimientos No Funcionales

### 5.1 Estetica y Diseno
- **Super moderna**, orientada a Gen Z
- Involucra **arte y artistas modernos** en el concepto visual
- Rebranding en proceso con nuevo arte y concepto
- Tema oscuro como base (`#101010`)
- Gradientes rojo-purpura como identidad visual
- Tipografia limpia y contemporanea (Aeonik)

### 5.2 Engagement
- Gamificacion como motor de retencion
- Modulos funcionan como **"hobbies"**: espacios donde el usuario habita y consume
- Contenido fresco constante (episodios, articulos, devocionales, eventos)
- Multiples creadores generando contenido para diversos segmentos

### 5.3 Contexto Cultural
- La logica operativa debe adaptarse a **Norteamerica y Latinoamerica** (el equipo anterior era de Beirut)
- Las iglesias cristianas tienen dinamica participativa, no dogmatica
- Multiples personas crean contenido, no solo una autoridad central

---

## 6. Restricciones y Consideraciones

- El diseno se construye **sobre algo ya existente**, no desde cero
- El equipo de desarrollo anterior tenia una logica operativa diferente (Beirut vs Americas)
- Se necesita **comunicacion constante** entre disenador y cliente por las dudas que surgen al trabajar sobre algo ya construido
- Ya existe un **dashboard de administracion** externo
- La autorizacion de eventos es un proceso manual/semi-automatico por ahora

---

## 7. Prioridades Identificadas

| Prioridad | Modulo / Feature |
|-----------|-----------------|
| Alta | Biblia (modulo principal, ya existe parcialmente) |
| Alta | Eventos / Boleteria (diferenciador clave de la app) |
| Alta | Pulir UI/UX de lo existente para logica Americas |
| Media | Devocionales por temas |
| Media | Gamificacion (puntos, progreso) |
| Media | App del operador/moderador |
| Baja | Guest/Podcast (contenido, no estructura critica) |
| Baja | Growth Tracks (complementario) |
