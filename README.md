# 🌊 Las Olas Más Extremas del Mundo

Sitio web sobre los destinos de surf más extremos del planeta, con galería interactiva, navegación lateral y diseño oceánico oscuro totalmente responsive.

---

## Vista previa del layout

```
┌──────────┬─────────────────────────────────────────┐
│          │  Las Olas Más Extremas del Mundo        │
│          ├─────────────────────────────────────────┤
│  nav     │  Ordenar por: [Atlántico ▼]             │
│  lateral ├─────────────────────────────────────────┤
│          │  ┌──────┐ ┌──────┐ ┌──────┐ ┌──────┐  │
│          │  │ card │ │ card │ │ card │ │ card │  │
│          │  └──────┘ └──────┘ └──────┘ └──────┘  │
│          │  ┌──────┐ ┌──────┐ ┌──────┐ ┌──────┐  │
│          │  │ card │ │ card │ │ card │ │ card │  │
│          │  └──────┘ └──────┘ └──────┘ └──────┘  │
├──────────┴─────────────────────────────────────────┤
│  🌐 Facebook   📷 Instagram   💬 WhatsApp   © ...  │  ← footer fijo
└────────────────────────────────────────────────────┘
```

---

## Descripción

**Las Olas Más Extremas del Mundo** es una página web estática que presenta una galería de los destinos de surf más reconocidos a nivel internacional: Australia, California, España, Hawái, Irlanda, México, Perú y Portugal. El diseño está inspirado en la profundidad del océano, con una paleta de azules abisales y acentos cian eléctrico que refuerzan la identidad visual del tema.

---

## Estructura del proyecto

```
olas-extremas/
│
├── index.html
├── README.md
└── assets/
    ├── css/
    │   └── style.css
    └── img/
        ├── 1ola.jpeg   → Australia
        ├── 2ola.jpeg   → California
        ├── 3ola.jpeg   → España
        ├── 4ola.jpeg   → Hawái
        ├── 5ola.jpeg   → Irlanda
        ├── 6ola.jpeg   → México
        ├── 7ola.jpeg   → Perú
        └── 8ola.jpeg   → Portugal
```

---

## Características principales

- **Navegación lateral** con logo, enlaces ancla a cada destino y botón de contacto
- **Galería responsiva** con efecto de transición blanco y negro → color al hacer hover
- **Footer fijo horizontal** en la parte inferior con enlaces a redes sociales
- **Diseño totalmente responsive** con tres breakpoints definidos
- **Filtro de ordenamiento** por océano (Atlántico, Pacífico, Mediterráneo)

---

## Efecto visual de la galería

Las imágenes aplican un efecto de revelado de color como metáfora visual del oleaje: en reposo aparecen en escala de grises y al pasar el cursor sobre ellas revelan su color original con una transición suave.

```css
/* Reposo — escala de grises */
img {
  filter: grayscale(100%) brightness(0.85);
  transform: scale(1.04);
  transition: filter 0.5s ease, transform 0.5s ease;
}

/* Hover — color completo */
div:hover img {
  filter: grayscale(0%) brightness(1);
  transform: scale(1);
}
```

La card completa también asciende levemente (`translateY(-6px)`) con un halo cian, simulando el levantamiento de una ola.

---

## Responsive — Media Queries

| Breakpoint | Nav | Galería | Footer |
|---|---|---|---|
| `≥ 992px` | Lateral 260px | **4 columnas** | Barra horizontal fija |
| `< 992px` | Lateral 220px | **2 columnas** | Barra horizontal fija |
| `< 576px` | **Barra superior** | **1 columna** | Barra horizontal fija |

En mobile la navegación lateral colapsa a una barra horizontal en la parte superior, con los botones de destino dispuestos en fila con wrap.

---

## Tecnologías

- HTML5 semántico
- CSS3 — Grid, Flexbox, Custom Properties, `position: fixed`, Media Queries, transiciones y transformaciones
- [Google Fonts](https://fonts.google.com) — `Bebas Neue` (display) + `DM Sans` (cuerpo)
- [Material Symbols](https://fonts.google.com/icons) — íconos `surfing` y `anchor`
- SVG inline — íconos de Facebook, Instagram y WhatsApp

---

## Paleta de colores

| Variable | Color | Uso |
|---|---|---|
| `--ocean-deep` | `#0a1628` | Fondo general |
| `--ocean-mid` | `#0d2137` | Nav, footer, surfaces |
| `--ocean-panel` | `#112944` | Cards y aside |
| `--cyan-surf` | `#00c9d4` | Acento principal — títulos, bordes, botones |
| `--cyan-light` | `#7ee8ed` | Acento suave — hover del botón Contacto |
| `--foam` | `#f0f4f8` | Texto principal |
| `--muted` | `#607b99` | Texto secundario y descripciones |

---

## Tipografía

- **Bebas Neue** — títulos de sección, nombres de destino y marca. Estilo condensado y de alto impacto, evoca carteles de competición de surf.
- **DM Sans** — cuerpo de texto, etiquetas y navegación. Moderna, legible y neutra para complementar el display.

---

## Footer

El footer es una barra fija anclada en la parte inferior de toda la pantalla (`position: fixed; bottom: 0; width: 100%`). Contiene:

- Enlace a **Facebook** con ícono SVG oficial
- Enlace a **Instagram** con gradiente de colores oficial
- Enlace a **WhatsApp** con ícono SVG oficial
- Texto de derechos reservados

Los elementos se distribuyen en fila horizontal con `justify-content: space-between`. El `main` tiene `padding-bottom` suficiente para que las cards no queden tapadas por la barra.

---

## Cómo usar

1. Clona o descarga el repositorio.
2. Agrega tus imágenes en `assets/img/` con los nombres `1ola.jpeg` a `8ola.jpeg`.
3. Abre `index.html` en el navegador — no requiere servidor ni instalación.

```bash
# Opcionalmente con servidor local:
npx serve .
# o
python -m http.server 8000
```

---

## Posibles mejoras

- Activar el select de ordenamiento con JavaScript para filtrar dinámicamente por océano.
- Agregar una página de detalle por destino al hacer clic en "Explorar".
- Implementar un mapa interactivo que muestre la ubicación de cada destino.
- Añadir animación de entrada a las cards al hacer scroll con `Intersection Observer`.
- Conectar el botón Contacto a un formulario o modal.

---

## Licencia

Proyecto de uso educativo. Libre para modificar y distribuir.