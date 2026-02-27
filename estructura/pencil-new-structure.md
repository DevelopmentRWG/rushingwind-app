# Estructura del archivo `pencil-new.pen`

> Version: 2.8
> Tipografia global: **Aeonik**
> Tema: Dark (`#101010` background)
> Colores primarios: `#ff0030` (rojo), `#7921f5` / `#5830f1` (purpura)

---

## Pantallas (Top-Level Frames)

El documento contiene **3 pantallas principales** a nivel raiz:

| # | ID | Nombre | Dimensiones | Posicion (x, y) |
|---|------|--------|-------------|------------------|
| 1 | `Gt57b` | **app-home** | 440 x 1098 | (0, 0) |
| 2 | `e5GK5` | **app-bible-sec** | 440 x 1494 | (1081, 0) |
| 3 | `vtCzT` | **app-bible-articles** | 440 x 1494 | (524, 4197) |

---

## 1. app-home (`Gt57b`) - Pantalla Principal

**440 x 1098 px** | fill: `#101010` | layout: none | clip: true

```
app-home
├── menu (S8si2) ─ Top bar 440x65
│   ├── bt-back (iTQok) ─ Boton retroceso [disabled]
│   │   ├── Ellipse 1 ─ Circulo gris #d9d9d9
│   │   └── Vector 2 ─ Flecha (path)
│   ├── Layer_1 (tP8OA) ─ Logo de la app (3 paths blancos)
│   │   ├── Vector (path)
│   │   ├── Vector (path)
│   │   └── Vector (path)
│   ├── menu-bt (1RR5r) ─ Hamburguesa [disabled]
│   │   ├── Rectangle 1 ─ Barra superior
│   │   ├── Rectangle 2 ─ Barra media
│   │   └── Rectangle 3 ─ Barra inferior
│   └── user-profile (rwjhf) ─ Avatar usuario 40x40
│       ├── Vector ─ Circulo fondo #d9d9d9
│       ├── Vector ─ Cabeza #060620
│       └── Vector ─ Cuerpo #060620
│
├── bible-sec (na6WR) ─ Tarjeta Bible (grupo)
│   ├── Rectangle 4 (JPiJA) ─ Fondo 390x228 con gradiente rojo→purpura
│   ├── "Bible" (Qrecr) ─ Texto 45px
│   └── "66 chapters" (LtjgH) ─ Texto 18px
│
├── points-sec (0Pg7a) ─ Tarjeta Earning Points (grupo)
│   ├── Rectangle 5 (luLxc) ─ Fondo rojo 193x137 rounded(25)
│   ├── "1350" (OUhTv) ─ Texto 35px
│   └── "Earning Points" (dQ35G) ─ Texto 16px
│
├── days-sec (7EjSU) ─ Tarjeta Knowledge Tracks (grupo)
│   ├── Rectangle 6 (Y4nL1) ─ Fondo gradiente rojo→purpura 187x137
│   ├── "12/ 26 completed" (uIimQ) ─ Texto 35px
│   └── "Knoledge Tracks" (lRhYk) ─ Texto 16px
│
├── bible-sec (fjbK0) ─ Tarjeta Bible Articles (grupo)
│   ├── Rectangle 7 (d8Hro) ─ Fondo gradiente rojo→purpura 390x178
│   └── "Bible Articles" (wJq26) ─ Texto 35px centrado
│
├── guest-sec (FgP1n) ─ Tarjeta Guest (grupo)
│   ├── Rectangle 8 (xkScM) ─ Fondo gradiente purpura→rojo 240x222
│   ├── "Guest" (QSUEE) ─ Texto 35px
│   └── "13 new episodes" (eDEsz) ─ Texto 16px
│
├── growth-sec (VOgYs) ─ Tarjeta Growth Tracks (grupo)
│   ├── Rectangle 9 (SvJ4V) ─ Fondo purpura #7921f5 141x222
│   ├── "5 days" (Rln3E) ─ Texto 35px
│   └── "Growth Tracks" (HpMyO) ─ Texto 16px
│
└── event-sec (f3aSf) ─ Tarjeta Events (grupo)
    ├── event-sec (pcNfp) ─ Fondo gradiente rojo→purpura 390x176
    ├── "In 3 days" (yCBQu) ─ Texto 16px
    └── Frame 2 (3fDxr) ─ Contenedor alineado derecha
        ├── "Events" (aGLMc) ─ Texto 35px align-right
        └── "Next Event Title" (avFYQ) ─ Texto 16px align-right
```

---

## 2. app-bible-sec (`e5GK5`) - Seccion Biblia

**440 x 1494 px** | fill: `#101010` | layout: none | clip: true

```
app-bible-sec
├── menu (kSXaq) ─ Top bar 440x65 (fill: #101010)
│   ├── bt-back (iKaXh) ─ Boton retroceso (visible)
│   │   ├── Ellipse 1 ─ Circulo gris
│   │   └── Vector 2 ─ Flecha (path)
│   ├── Layer_1 (iDx9s) ─ Logo [disabled]
│   ├── menu-bt (A4Gc1) ─ Hamburguesa [disabled]
│   └── user-profile (srcHW) ─ Avatar usuario
│
├── Frame 12 (A1Vyp) ─ Tabs de navegacion (390px)
│   ├── bt-books (5wQwW) ─ Tab "All Books" (390px, activo)
│   │   ├── Frame 11 → "All Books" (texto 22px)
│   │   └── Line 1 ─ Separador blanco
│   ├── bt-chap (lnSKN) ─ Tab "Chapter" (182px)
│   │   ├── Frame 11 → "Chapter" (texto 22px)
│   │   └── Line 1 ─ Separador blanco
│   └── bt-vers (J0Kca) ─ Tab "Verses" (181px)
│       ├── Frame 11 → "Verses" (texto 22px)
│       └── Line 1 ─ Separador blanco
│
└── Frame 17 (Z6J5j) ─ Lista de libros (390px, vertical, gap: 21)
    │
    ├── Frame 16 (J5Q4R) ─ Encabezado seccion
    │   ├── "Old testament: Book of the law" ─ Texto 12px
    │   └── Line 2 ─ Separador blanco
    │
    ├── sec-book (x8kF3) ─ Libro: Genesis (Book 1)
    │   ├── Rectangle 12 ─ Miniatura 148x123 (gradiente, opacity 0.5)
    │   └── Frame 20 → Frame 15 + Frame 19
    │       ├── "Book 1" ─ 14px
    │       ├── "Genesis" ─ 22px (#bfbfbf)
    │       ├── "50/50 Chapters" ─ 12px (#bfbfbf)
    │       ├── "6h50m reading" ─ 10px (#9e9e9e)
    │       └── bt-read-chapter (T6uXi) ─ Boton "Read now" (borde gradiente)
    │           ├── "Read now" ─ 12px
    │           └── Icono flecha (circulo blanco + vector purpura)
    │
    ├── sec-book (DiESY) ─ Libro: Exodus (Book 2)
    │   ├── Rectangle 12 ─ Miniatura (gradiente, opacity 0.5)
    │   └── Frame 20 → misma estructura
    │       ├── "Book 2" / "Exodus" / "40/40 Chapters"
    │       └── bt-read-chapter ─ Boton "Read now" (borde gradiente)
    │
    ├── sec-book (XGaV4) ─ Libro: Leviticus (Book 3)
    │   ├── Rectangle 12 ─ Miniatura (gradiente)
    │   └── Frame 20 → misma estructura
    │       ├── "Book 3" / "Leviticus" / "0/27 Chapters"
    │       └── bt-read-chapter (IpXiw) ─ Boton "Read now" (fill gradiente)
    │
    ├── sec-book (iAQx8) ─ Libro: Genesis (Book 1, repetido)
    │   └── ... (misma estructura)
    │
    ├── sec-book (pJcdI) ─ Libro: Genesis (Book 1, repetido)
    │   └── ... (misma estructura)
    │
    ├── Frame 17 (BTSgj) ─ Encabezado seccion
    │   ├── "new testament: hitorical" ─ Texto 12px
    │   └── Line 2 ─ Separador blanco
    │
    ├── sec-book (cJYgF) ─ Libro NT (gradiente invertido)
    │   └── ... (misma estructura, boton con fill + stroke gradiente)
    │
    ├── sec-book (0Tij8) ─ Libro NT
    │   └── ... (misma estructura)
    │
    └── sec-book (yGd3o) ─ Libro NT
        └── ... (misma estructura)
```

---

## 3. app-bible-articles (`vtCzT`) - Articulos de la Biblia

**440 x 1494 px** | fill: `#101010` | layout: none | clip: true

```
app-bible-articles
├── menu (swfzv) ─ Top bar 440x65 (fill: #101010)
│   ├── bt-back (X2geH) ─ Boton retroceso (visible)
│   ├── Layer_1 (DzPFX) ─ Logo [disabled]
│   ├── menu-bt (n379O) ─ Hamburguesa [disabled]
│   └── user-profile (zR3Fm) ─ Avatar usuario
│
└── Frame 46 (cLO1G) ─ Contenido principal (390px, vertical, gap: 23)
    │
    ├── Frame 43 (qY5zN) ─ Header seccion
    │   ├── Frame 42 (0v8rw) ─ Titulo y descripcion
    │   │   ├── "The Bible explained" ─ 22px
    │   │   └── "Search for all articles in our encyclopedia" ─ 16px
    │   └── Frame 41 (jsIcZ) ─ Barra de busqueda
    │       ├── "Search for subject..." ─ 18px (#5e5e5e)
    │       └── Line 4 ─ Separador gris
    │
    ├── Article Card 1 (xrJw5) ─ 390x243 (fill: #5830f1, rounded: 27)
    │   ├── Frame 44 → Frame 28 (Speaker info)
    │   │   ├── user-profile (nbCdb) ─ Avatar 40x40 negro
    │   │   ├── "Speaker Name" ─ 18px
    │   │   └── "1:02" ─ 18px (#876af7)
    │   ├── "Lorem ipsum..." ─ 18px (500 weight, descripcion)
    │   └── bt-read-chapter (C6kUO) ─ "Read now" (fill: #ff0030)
    │
    ├── Article Card 2 (YucLT) ─ misma estructura
    │   └── ...
    │
    ├── Article Card 3 (lblGg) ─ misma estructura
    │   └── ...
    │
    ├── Article Card 4 (oNgIL) ─ misma estructura
    │   └── ...
    │
    └── Article Card 5 (QOFX6) ─ misma estructura
        └── ...
```

---

## Componentes Reutilizables

### Menu / Top Bar
Presente en las 3 pantallas con estructura consistente:
- **bt-back**: Circulo gris con flecha (path)
- **Layer_1**: Logo de la app (3 vectores blancos)
- **menu-bt**: Icono hamburguesa (3 rectangulos grises)
- **user-profile**: Avatar (circulo + silueta persona)

### sec-book (Tarjeta de Libro)
Patron repetido en `app-bible-sec`:
- Miniatura con gradiente (148x123, rounded: 10)
- Info del libro (numero, nombre, capitulos)
- Tiempo de lectura
- Boton "Read now" con icono flecha

### Article Card (Tarjeta de Articulo)
Patron repetido en `app-bible-articles`:
- Fondo purpura `#5830f1` (rounded: 27)
- Avatar + nombre del speaker + duracion
- Texto descriptivo (lorem ipsum)
- Boton "Read now" rojo `#ff0030`

### bt-read-chapter (Boton "Read now")
- Pill shape (cornerRadius: 62)
- Variantes: solo borde gradiente / fill gradiente / fill rojo solido
- Contiene texto "Read now" + icono circular con flecha

---

## Paleta de Colores

| Color | Hex | Uso |
|-------|-----|-----|
| Background | `#101010` | Fondo de todas las pantallas |
| Rojo primario | `#ff0030` | Tarjetas, botones, gradientes |
| Purpura primario | `#7921f5` | Tarjetas, gradientes |
| Purpura secundario | `#5830f1` | Fondos de articulos, gradientes |
| Blanco | `#ffffff` | Textos principales, iconos |
| Gris claro | `#d9d9d9` | Avatares, iconos menu |
| Gris texto | `#bfbfbf` | Nombres de libros, subtextos |
| Gris muted | `#9e9e9e` | Tiempos de lectura |
| Gris oscuro | `#5e5e5e` | Placeholder busqueda |
| Purpura claro | `#876af7` | Duracion en articulos |
| Negro perfil | `#060620` | Silueta persona en avatar |

---

## Tipografia

| Fuente | Pesos | Tamanos usados |
|--------|-------|----------------|
| **Aeonik** | 300 (Light), normal (400), 500 (Medium) | 10, 12, 14, 16, 18, 22, 35, 45 px |

---

## Notas de Diseno

1. **Layout**: Las pantallas usan `layout: none` (posicionamiento absoluto) excepto los contenedores internos que usan vertical/horizontal con `gap`.
2. **Gradientes**: Se usan gradientes lineales rojo-purpura y purpura-rojo en tarjetas y botones.
3. **Clip**: Todas las pantallas tienen `clip: true` para contener el scroll.
4. **Patron de tarjetas**: Las tarjetas en `app-home` usan `group` con posicionamiento absoluto, mientras que en `app-bible-sec` y `app-bible-articles` usan frames con auto-layout.
5. **Estados**: Algunos elementos tienen `enabled: false` (bt-back en home, logos y hamburguesas en pantallas internas).
