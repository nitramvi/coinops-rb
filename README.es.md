# CoinOPS-RB

> 🌎 *English: see [README.md](README.md).*

Un tema **estilo CoinOPS** para **RetroBat** (EmulationStation / Batocera), pensado para reproducir el look del
tema **CoinOPS de ES-DE** dentro del motor de RetroBat.

Recrea la estética CoinOPS clásica: cada juego dentro de un **gabinete/TV** con su video, una **rueda (wheel) de
marquees** a la derecha, el **fanart** del juego de fondo, y una vista de sistemas con el **fanart grande**, el
logo del sistema y una **descripción larga** por consola.

> ⚠️ Este NO es un port directo: ES-DE y RetroBat usan **motores de temas distintos e incompatibles**. El tema fue
> **reconstruido** en el formato de RetroBat (Batocera EmulationStation) reutilizando los assets originales.

---

## 📸 Capturas

| Vista de juegos | Vista de sistemas |
| :---: | :---: |
| ![Vista de juegos](preview/gamelist.png) | ![Vista de sistemas](preview/system.png) |

![Wheel](preview/wheel.png)

---

## 🧩 Basado en / Créditos

Este tema es un trabajo derivado. Todo el crédito a los autores originales:

- **Base / motor del tema:** [Alekfull-ARTFLIX](https://github.com/fagnerpc/Alekfull-ARTFLIX) por **fagnerpc**.
  La infraestructura (vistas, subsets, carga por sistema, efectos) viene de Artflix.
- **Look y assets CoinOPS:** [coinops-es-de](https://github.com/TheGrizzMD/coinops-es-de) por **TheGrizzMD**, que a su
  vez es un mashup de:
  - CoinOPS por **BritneysPAIRS (BP)** y **gjsmsmith**
  - **ARTFLIX** por **Alekfull (fagnerpc)**
  - **ARTFLIX-Cobalto** por **Galisteo (galisteogames)**
- **Adaptación a RetroBat / CoinOPS-RB:** reconstrucción de la vista de juegos y de sistemas en el formato de RetroBat,
  swap de cabinets/fanart a las versiones de CoinOPS, port de las descripciones por sistema, y ajustes finos
  calibrados contra ES-DE.

Cabinets, fanart, fuentes (Exo2), siluetas de control, iconos y descripciones provienen de coinops-es-de / Artflix.

---

## ✨ Características

- **Vista de juegos (CoinOPS Wheel):** gabinete/TV por sistema, video del juego dentro de la pantalla (con fallback
  video → screenshot → titlescreen), fanart del juego de fondo con viñeta, **rueda curva de marquees** (con loop
  continuo para listas cortas), carátula, barra inferior y columna de datos (System / Lanzamiento / Tiempo / etc.).
- **Vista de sistemas (CoinOPS):** fanart a pantalla completa, viñeta circular, logo del sistema a la izquierda,
  **descripción larga del sistema en español** y silueta del control.
- **Descripciones por sistema:** 172 consolas con su descripción larga (portadas de coinops-es-de), en
  `./<sistema>/sysdesc.xml`, que solo se muestran en la vista de sistemas CoinOPS.
- **Cabinet por defecto:** los sistemas sin gabinete propio usan una TV genérica con pared de ladrillo.
- **Menú limpio:** se dejó únicamente la vista CoinOPS (se quitaron las ~25 vistas extra de Artflix).

---

## 🚀 Instalación y uso

1. Copiá la carpeta **`CoinOPS-RB`** a `…/emulationstation/.emulationstation/themes/`.
2. En RetroBat: **UI Settings / Ajustes de interfaz → Theme Set → CoinOPS-RB**.
3. **Vista de sistemas:** en el menú del tema, elegí la vista de sistema **"CoinOPS"**.
4. La **vista de juegos** ya viene por defecto (CoinOPS Wheel).

### Scraping (importante)

Los medios **por juego** (fanart, marquee, screenshot, video) los baja **el scraper de RetroBat**, no el tema.
Para que se vea completo:

> **Menú → Scraper → fuente ScreenScraper**, y activá **Fanart, Marquee/Wheel, Box (carátula), Screenshot y Video**.

Sin fanart por juego no se ve el fondo de la derecha; sin marquee no se ven los logos de la rueda.

---

## 🔧 Estructura (para tocar a futuro)

| Archivo / carpeta | Qué hace |
|---|---|
| `theme.xml` | Raíz (base Artflix). Incluye las vistas y subsets. `defaultView="gamecarousel"`. |
| `coinops-wheel.xml` | **Vista de juegos** (la rueda CoinOPS). Acá se ajusta wheel, video, fanart, metadata, barra. |
| `systemview/coinops.xml` | **Vista de sistemas** CoinOPS. |
| `<sistema>/sysdesc.xml` | Descripción larga por sistema (solo se muestra en la vista CoinOPS). |
| `assets/coinops/*.png` | Gabinetes/TV por sistema (`default.png` = fallback ladrillo). |
| `assets/arts/hd/*.jpg` | Fanart de sistema en 1080p. |
| `assets/controllers/*.svg` | Siluetas de control para la vista de sistemas. |

Ajustes típicos de la rueda (en `coinops-wheel.xml`, elemento `<gamecarousel>`):
`logoSize` (tamaño), `logoScale` (cuánto más grande el seleccionado), `logoRotation` / `logoRotationOrigin` (curva),
`maxLogoCount` (cantidad), `minLogoOpacity` (opacidad de los no-seleccionados), `scrollLoop` (loop continuo).

---

## ⚠️ Limitaciones conocidas (del motor de RetroBat, no del tema)

- **Nitidez fina:** el escalador de RetroBat agranda imágenes con menos suavizado que ES-DE; los logos grandes
  pierden un pelín de filo. Es del motor; no se puede igualar por tema.
- ES-DE corre un motor de render más nuevo, así que el 100% pixel-perfect no es alcanzable.

---

## 📜 Licencia

Trabajo derivado de Alekfull-ARTFLIX y coinops-es-de, ambos bajo **Creative Commons CC-BY-NC-SA**.
Este tema mantiene la misma licencia: **no comercial**, con atribución y compartir-igual.

- ✅ Uso personal, modificar, compartir (con atribución).
- ❌ Uso comercial.
