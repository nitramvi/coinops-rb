# CoinOPS-RB

A **CoinOPS-style theme** for **RetroBat** (EmulationStation / Batocera), built to recreate the look of the
**CoinOPS theme from ES-DE** inside RetroBat's engine.

It brings back the classic CoinOPS feel: every game inside a **cabinet/TV** playing its video, a **vertical wheel
of marquees** on the right, the game's **fanart** in the background, and a system view with a large **fanart**,
the system logo and a **long per-system description**.

> 🌎 *Español: ver [README.es.md](README.es.md).*

> ⚠️ This is NOT a direct port: ES-DE and RetroBat use **different, incompatible theme engines**. The theme was
> **rebuilt** in RetroBat's format (Batocera EmulationStation) reusing the original assets.

---

## 📸 Screenshots

| Gamelist view | System view |
| :---: | :---: |
| ![Gamelist view](preview/gamelist.png) | ![System view](preview/system.png) |

![Wheel](preview/wheel.png)

---

## 🧩 Based on / Credits

This is a derivative work. All credit to the original authors:

- **Base / theme engine:** [Alekfull-ARTFLIX](https://github.com/fagnerpc/Alekfull-ARTFLIX) by **fagnerpc**.
  The infrastructure (views, subsets, per-system loading, effects) comes from Artflix.
- **CoinOPS look & assets:** [coinops-es-de](https://github.com/TheGrizzMD/coinops-es-de) by **TheGrizzMD**, which is
  itself a mashup of:
  - CoinOPS by **BritneysPAIRS (BP)** and **gjsmsmith**
  - **ARTFLIX** by **Alekfull (fagnerpc)**
  - **ARTFLIX-Cobalto** by **Galisteo (galisteogames)**
- **RetroBat adaptation / CoinOPS-RB:** rebuilt the gamelist and system views in RetroBat's format, swapped
  cabinets/fanart to the CoinOPS versions, ported the per-system descriptions, and fine-tuned everything against ES-DE.

Cabinets, fanart, fonts (Exo2), controller outlines, icons and descriptions come from coinops-es-de / Artflix.

---

## ✨ Features

- **Gamelist (CoinOPS Wheel):** per-system cabinet/TV, the game's video inside the screen (with a
  video → screenshot → titlescreen fallback), the game's fanart in the background with a vignette, a **curved wheel
  of marquees** (continuous loop so short lists still fill the wheel), boxart, a bottom bar and a data column
  (System / Release / Play Time / etc.).
- **System view (CoinOPS):** full-screen fanart, circular vignette, the system logo on the left, a **long system
  description** and the controller outline.
- **Per-system descriptions:** 172 systems with their long description (ported from coinops-es-de), in
  `./<system>/sysdesc.xml`, shown only in the CoinOPS system view. **Bilingual** — English by default, Spanish when
  the UI language is Spanish.
- **Default cabinet:** systems without their own cabinet use a generic TV on a brick wall.
- **Clean menu:** only the CoinOPS view is kept (the ~25 extra Artflix views were removed).

---

## 🚀 Installation & usage

1. Copy the **`CoinOPS-RB`** folder into `…/emulationstation/.emulationstation/themes/`.
2. In RetroBat: **UI Settings → Theme Set → CoinOPS-RB**.
3. **System view:** in the theme menu, choose the **"CoinOPS"** system view.
4. The **gamelist** is the default (CoinOPS Wheel).

### Scraping (important)

The **per-game** media (fanart, marquee, screenshot, video) is downloaded by **RetroBat's scraper**, not the theme.
For the full look:

> **Menu → Scraper → ScreenScraper source**, and enable **Fanart, Marquee/Wheel, Box, Screenshot and Video**.

Without per-game fanart there's no right-side background; without marquees there are no wheel logos.

---

## 🔧 Structure (for future edits)

| File / folder | What it does |
|---|---|
| `theme.xml` | Root (Artflix base). Includes the views and subsets. `defaultView="gamecarousel"`. |
| `coinops-wheel.xml` | **Gamelist view** (the CoinOPS wheel). Tune wheel, video, fanart, metadata, bar here. |
| `systemview/coinops.xml` | **System view** (CoinOPS). |
| `<system>/sysdesc.xml` | Per-system long description (shown only in the CoinOPS view). |
| `assets/coinops/*.png` | Per-system cabinets/TV (`default.png` = brick fallback). |
| `assets/arts/hd/*.jpg` | 1080p system fanart. |
| `assets/controllers/*.svg` | Controller outlines for the system view. |

Common wheel tweaks (in `coinops-wheel.xml`, `<gamecarousel>` element):
`logoSize` (size), `logoScale` (how much bigger the selected one is), `logoRotation` / `logoRotationOrigin` (curve),
`maxLogoCount` (count), `minLogoOpacity` (non-selected opacity), `scrollLoop` (continuous loop).

---

## ⚠️ Known limitations (RetroBat engine, not the theme)

- **Fine sharpness:** RetroBat's scaler upsamples images with less smoothing than ES-DE, so large logos lose a bit
  of crispness. This is an engine trait; it can't be matched via the theme.
- ES-DE runs a newer rendering engine, so 100% pixel-perfect parity isn't achievable.

---

## 📜 License

Derivative of Alekfull-ARTFLIX and coinops-es-de, both under **Creative Commons CC-BY-NC-SA**.
This theme keeps the same license: **non-commercial**, attribution, share-alike.

- ✅ Personal use, modify, share (with attribution).
- ❌ Commercial use.
