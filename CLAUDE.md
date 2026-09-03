# Ygar Studio — GitHub Pages

Static GitHub Pages site for **Ygar Studio**, an independent Android game studio.

## Conventions

- Each app gets its own subfolder (`enko/`, `igi/`, future apps follow the same pattern). Every app has `index.html` + `privacy-policy.html`, an `<app>:` i18n namespace (+ a `<app>_privacy:` one), an icon SVG in `assets/`, and a card in the home "Our Games" grid.
- All pages use **Tailwind CSS CDN** with a shared custom config (colors + font families).
- **Bilingual** EN/FR via the `jekyll-multiple-languages-plugin` (`{% t namespace.key %}`, `/fr/` path prefix, `lang_en` / `lang_fr` front-matter) — NOT a JS toggle.
- The **studio shell is shared and constant**: `_layouts/default.html` nav + footer use the dark-lapis studio chrome and the gold Macondo "Ygar" wordmark on every page.

### Per-app identity (SPEC)

Each app page must reflect **its own app's** look so it reads as that product, not a studio template. The shared shell (nav/footer) stays studio chrome; the page **content** between them carries the app's identity:

- **Pull the palette, fonts, and mood from the app's own `docs/DESIGN.md`** (in its Android repo). Use inline styles / a scoped `<style>` since the Tailwind config only holds the default (Enko) tokens.
- **Gameplay copy comes from the app itself** — store `description_{en,fr}.md` and the in-app tutorial/didacticiel strings (`values*/strings.xml`) — so the site matches the real rules (e.g. player counts, objectives). Keep numbers in sync with the app (`MAX_PLAYERS` etc.).
- Keep EN + FR i18n keys in sync (1:1 in `_i18n/en.yml` and `_i18n/fr.yml`).

| App | Page identity | Source repo |
|---|---|---|
| **Enko Clues** | Dark lapis page (`#050D1F`), **purple** accent (`#7C3AED`), Noto Serif body. Matches the shared default config. | `C:\Users\Sesa725153\AndroidStudioProjects\enko` |
| **City Transport** | **Printed transit plan**: warm paper page (`#f4f1e9`), dark-ink text (`#2c3542`/`#1f2733`), water-blue rules (`#a7cbe8`), teal-slate eyebrows (`#315963`), white map tiles with `#dcd6c8` borders, green signal CTA (`#1fa45b`). Line hues (metro blue `#2569cd`, green, amber) are **accents only** — in the game a hue means a line, so they must never become page furniture. Titles **Noto Sans** with wide tracking, not Metamorphous: a decorative face fights a schematic map. | `C:\Users\Sesa725153\AndroidStudioProjects\CityTransport` |
| **Ygar Solitaire** | **The card table**: deep green ground (`#0C2B25`→`#0F3D33`), paper card faces (`#F6F1E6`), ink text (`#1E2126`), the studio gold (`#D4A832`) used only as a rule/accent, red (`#B93F36`) for the red suits and hint teal (`#3E8E7E`) for links. Noto Sans throughout — the app reserves Macondo Swash Caps for its splash wordmark, so the studio's Metamorphous title face is deliberately unused here. | `C:\Users\Sesa725153\AndroidStudioProjects\solitaire` |
| **Igi** | **Cream parchment** page (`#F5EBD6`→`#E8D9B8`→`#C9B084`), **ink-sepia** text (`#4A3A2E`/`#2A1F18`), **slate/gold** chrome cards (`#1A2237`/`#222C44` + `#C9A24B`), **gold stone-seal** CTA, joker-hat mascot, harlequin-diamond dividers, jewel accents. Titles **Metamorphous**, body **Noto Sans** — **Noto Serif is banned** (mirrors the app's font rule). | `C:\Users\Sesa725153\AndroidStudioProjects\igi` |

## Source assets

All original assets live in **`C:\Users\Sesa725153\AndroidStudioProjects\enko`**:

| Asset | Source path |
|---|---|
| Studio logo SVG | `assets/ygar_studio_logo.svg` |
| App icon (Android vector) | `app/src/main/res/drawable/ic_launcher_foreground.xml` |
| Feature graphic SVG | `store/feature_graphic.svg` |
| Studio header SVG | `store/ygar_studio_header.svg` |
| Store screenshots | `store/Screenshot_*.jpg` |
| App description (EN) | `store/description_en.md` |
| App description (FR) | `store/description_fr.md` |
| Colors | `app/src/main/res/values/colors.xml` |

## Design tokens (Tailwind config)

Shared config — Enko accent colors. Studio home uses gold overrides via inline styles.

| Token | Value | Usage |
|---|---|---|
| dark | `#050D1F` | Page background |
| card | `#0D1330` | Card background |
| accent | `#7C3AED` | Enko purple (buttons, borders) |
| accent-light | `#818CF8` | Enko purple light (labels) |
| border | `#2D1A4A` | Card/section borders |
| border-light | `#3D2A5A` | Hover borders |
| muted | `#9CA3AF` | Secondary text |

Studio home gold overrides (inline styles):
- Gold accent: `#D4A947`
- Hero glow: `rgba(185,132,12,0.14)`

Studio logo (`assets/logo.svg`): gold extrusion `#1A1200` → `#916E00`, white front face.

## Typography
- **Studio logo**: Macondo Swash Caps (Google Font) — must be used for 'ygar' in studio logo.
- **Titles**: Metamorphous (Google Font)
- **Body / UI text**: Noto Sans (Google Font) — clean, readable sans-serif with broad Unicode support

## App info

**Enko Clues**
- **Package**: `com.ygar.app.enko`
- **Play Store**: `https://play.google.com/store/apps/details?id=com.ygar.app.enko`
- **Source assets**: `C:\Users\Sesa725153\AndroidStudioProjects\enko`

**City Transport**
- **Package**: `com.ygar.app.citytransport`
- **Play Store**: `https://play.google.com/store/apps/details?id=com.ygar.app.citytransport` (Draft — closed testing as of 2026-09-02)
- **Icon**: `assets/citytransport-icon.svg` — generated from the SAME fractional geometry as
  the app's own `tools/gen_logo.py`, so the site mark and the launcher icon are one drawing.
- **Source assets**: `C:\Users\Sesa725153\AndroidStudioProjects\CityTransport`

**Ygar Solitaire**
- **Package**: `com.ygar.app.solitaire`
- **Play Store**: **not published yet** — pre-launch (device hardening / internal testing
  still open in its ROADMAP). The page links to the store URL anyway, as City Transport's does.
- **Icon**: `assets/solitaire-icon.svg` — the app's own `docs/store/icon.svg` geometry
  verbatim, cross-checked against `res/drawable/ic_launcher_foreground.xml`.
- **Free forever**: no ads, no IAP, no paid version (its SPEC §1.3 makes that a rule, not a
  current state) — so its policy is the simplest of the four: VIBRATE only, no network.
- **Source assets**: `C:\Users\Sesa725153\AndroidStudioProjects\solitaire`

**Igi**
- **Package**: `com.ygar.app.igi`
- **Play Store**: `https://play.google.com/store/apps/details?id=com.ygar.app.igi`
- **Icon**: `assets/igi-icon.svg` (joker-hat crest on slate, derived from the Igi launcher vector)
- **Source assets**: `C:\Users\Sesa725153\AndroidStudioProjects\igi`

- **Publisher**: Ygar Studio 𒅗𒃻
- **Contact**: ygar.studio@gmail.com

## Privacy policy

- One per app: `enko/privacy-policy.html` (`privacy:` namespace), `igi/privacy-policy.html`
  (`igi_privacy:`), `citytransport/privacy-policy.html` (`citytransport_privacy:`) and
  `solitaire/privacy-policy.html` (`solitaire_privacy:`).
- Enko covers optional Google Play Games cloud save + INTERNET permission; Igi is fully offline
  (no network access, no cloud, no third-party services); **City Transport** is offline too but
  has **in-app purchases**, so its policy carries a Play Billing section and declares the
  `com.android.vending.BILLING` permission alongside `VIBRATE`.
- **Both languages must be kept in sync** when updating policy text.
- City Transport's policy is a MIRROR: the source of truth is `docs/legal/privacy-policy.md` in
  the app repo, and the app links here (`PRIVACY_URL` in `game/scripts/ui/settings.gd`). Change
  one, change the other.
